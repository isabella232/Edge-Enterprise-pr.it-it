---
title: Accedere alla versione precedente di Microsoft Edge
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 08/17/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Scopri come accedere alla versione legacy di Microsoft Edge.
ms.openlocfilehash: e5a97a487dc6b3a45504a721e460a69103b0174e
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980253"
---
# <span data-ttu-id="36b5d-103">Accedere a Microsoft Edge Legacy dopo l'installazione della nuova versione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36b5d-103">Access Microsoft Edge Legacy after installing the new version of Microsoft Edge</span></span>

<span data-ttu-id="36b5d-104">Scopri come accedere a Microsoft Edge Legacy dopo l'installazione della nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-104">Learn how to access Microsoft Edge Legacy after installing the new version of Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="36b5d-105">Questo articolo si applica al [canale Stable](microsoft-edge-channels.md) di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-105">This article applies to the Microsoft Edge [Stable channel](microsoft-edge-channels.md).</span></span>

<span data-ttu-id="36b5d-106">Anche se la maggior parte delle organizzazioni vorrà sostituire la versione legacy di Microsoft Edge con la nuova versione, esistono alcune situazioni in cui gli utenti avranno bisogno di accedere a entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="36b5d-106">While most organizations will want to replace Microsoft Edge Legacy with the new version, there are some situations where users will need access to both versions.</span></span> <span data-ttu-id="36b5d-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="36b5d-107">For example:</span></span>

- <span data-ttu-id="36b5d-108">personale dell'helpdesk e del supporto, che interagisce con gli utenti che usano una o entrambe le versioni di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-108">Helpdesk and support staff who interact with users who are using either or both versions of Microsoft Edge.</span></span>
- <span data-ttu-id="36b5d-109">Sviluppatori che supportano i clienti che usano una o entrambe le versioni di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-109">Developers who support customers who are using either or both versions of Microsoft Edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36b5d-110">Non si consiglia l'esecuzione della Versione legacy di Microsoft Edge in modalità affiancata alla nuova versione di Microsoft Edge per l'uso in produzione.</span><span class="sxs-lookup"><span data-stu-id="36b5d-110">Running Microsoft Edge Legacy side-by-side with the new version of Microsoft Edge is not recommended for use in production.</span></span> <span data-ttu-id="36b5d-111">Questa configurazione dovrebbe essere usata solo in casi specifici in cui è necessario eseguire test con entrambe le versioni del browser.</span><span class="sxs-lookup"><span data-stu-id="36b5d-111">This configuration should only be used in specific cases where testing with both browser versions is required.</span></span>
>
> <span data-ttu-id="36b5d-112">Il supporto per l'app desktop della Versione legacy di Microsoft Edge terminerà il 9 marzo 2021 in favore del nuovo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-112">The Microsoft Edge Legacy desktop app will reach end of support on March 9, 2021 in favor of the new Microsoft Edge.</span></span> <span data-ttu-id="36b5d-113">Ciò significa che la Versione legacy di Microsoft Edge non riceverà gli aggiornamenti della sicurezza dopo tale data.</span><span class="sxs-lookup"><span data-stu-id="36b5d-113">This means that Microsoft Edge Legacy will not receive security updates after that date.</span></span> <span data-ttu-id="36b5d-114">Questa modifica è applicabile a tutte le esperienze eseguite nell'app desktop della Versione legacy di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-114">This change is applicable to all experiences that run in the Microsoft Edge Legacy desktop app.</span></span> <span data-ttu-id="36b5d-115">[Ulteriori informazioni](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).</span><span class="sxs-lookup"><span data-stu-id="36b5d-115">[Learn more](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).</span></span>

## <span data-ttu-id="36b5d-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="36b5d-116">Before you begin</span></span>

<span data-ttu-id="36b5d-117">Le procedure illustrate in questo articolo si applicano ai sistemi che sono stati aggiornati con gli ultimi aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="36b5d-117">The procedures in this article apply to systems that have been updated with the latest security updates.</span></span> <span data-ttu-id="36b5d-118">Quando verrà installata la nuova versione di Microsoft Edge, la versione precedente (Microsoft Edge Legacy) verrà nascosta.</span><span class="sxs-lookup"><span data-stu-id="36b5d-118">When the new version of Microsoft Edge is installed, the old version (Microsoft Edge Legacy) will be hidden.</span></span> <span data-ttu-id="36b5d-119">Per impostazione predefinita, tutti i tentativi di avviare la versione precedente reindirizzeranno l'utente alla versione installata di recente di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-119">By default, all attempts to launch the old version will redirect the user to the newly installed version of Microsoft Edge.</span></span> <span data-ttu-id="36b5d-120">Questo articolo descrive come si può continuare a usare la versione legacy di Microsoft Edge dopo l'installazione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-120">This article describes how you can keep using Microsoft Edge Legacy after you install Microsoft Edge.</span></span>

## <span data-ttu-id="36b5d-121">Guida introduttiva: Esperienza affiancata con il canale beta di Microsoft Edge e la Versione legacy di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36b5d-121">Quickstart: Side-by-side experience with Microsoft Edge Beta Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="36b5d-122">Prima di usare le istruzioni dettagliate di questo articolo, tenere presente che i due passaggi seguenti consentono agli utenti di eseguire la Versione legacy di Microsoft Edge e il [canale beta](microsoft-edge-channels.md) di Microsoft Edge in modalità affiancata.</span><span class="sxs-lookup"><span data-stu-id="36b5d-122">Before using the detailed instructions in this article, consider the following two steps to let your users run Microsoft Edge Legacy and the Microsoft Edge [Beta channel](microsoft-edge-channels.md) side-by-side.</span></span>

1. <span data-ttu-id="36b5d-123">Impedisci l'installazione automatica del canale Stable di Microsoft Edge da [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq).</span><span class="sxs-lookup"><span data-stu-id="36b5d-123">Prevent the automatic install of the Stable Channel of Microsoft Edge by [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq).</span></span>

   > [!TIP]
   > <span data-ttu-id="36b5d-124">Utilizza [Blocker Toolkit](microsoft-edge-blocker-toolkit.md) per disabilitare la distribuzione automatica di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-124">Use the [Blocker Toolkit](microsoft-edge-blocker-toolkit.md) to disable automatic delivery of Microsoft Edge.</span></span>

2. <span data-ttu-id="36b5d-125">Installare il [canale Beta](https://www.microsoft.com/edge/business/download) della nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-125">Install the [Beta channel](https://www.microsoft.com/edge/business/download) of the new version of Microsoft Edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="36b5d-126">Leggere [Altre informazioni](#additional-information) per informazioni sulle impostazioni della chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="36b5d-126">Read [Additional information](#additional-information) for information about Registry Key settings.</span></span>

<span data-ttu-id="36b5d-127">Questa soluzione affiancata è meno complessa e richiede meno gestione rispetto alla soluzione dettagliata descritta in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="36b5d-127">This side-by-side solution is less complex and requires less management than the detailed solution described in this article.</span></span> <span data-ttu-id="36b5d-128">Tuttavia, sarà necessario eseguire il canale beta al posto del canale stabile.</span><span class="sxs-lookup"><span data-stu-id="36b5d-128">However, this solution does mean that you'll be running the Beta Channel rather than the Stable Channel.</span></span>

## <span data-ttu-id="36b5d-129">Esperienza affiancata con il canale stabile di Microsoft Edge e la Versione legacy di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36b5d-129">Side-by-side experience with Microsoft Edge Stable Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="36b5d-130">Installando il canale Stable della versione successiva di Microsoft Edge a livello di sistema, la versione corrente (Microsoft Edge Legacy) verrà nascosta.</span><span class="sxs-lookup"><span data-stu-id="36b5d-130">Installing the Stable Channel of the next version of Microsoft Edge at the system-level will cause the current version (Microsoft Edge Legacy) to be hidden.</span></span> <span data-ttu-id="36b5d-131">Se si vuole permettere agli utenti di vedere entrambe le versioni di Microsoft Edge affiancate in Windows, è possibile abilitare questa esperienza impostando il criterio di gruppo **Consenti esperienza browser Microsoft Edge affiancata** su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="36b5d-131">If you want to let your users see both versions of Microsoft Edge side by side in Windows, you can enable this experience by setting the **Allow Microsoft Edge Side by Side browser experience** group policy to **Enabled**.</span></span>

<span data-ttu-id="36b5d-132">Questo criterio di gruppo è documentato [qui](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)</span><span class="sxs-lookup"><span data-stu-id="36b5d-132">This group policy is documented [here](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)</span></span>

### <span data-ttu-id="36b5d-133">Per configurare il criterio dell'esperienza browser affiancata:</span><span class="sxs-lookup"><span data-stu-id="36b5d-133">To set up the side-by-side browser experience policy:</span></span>

1. <span data-ttu-id="36b5d-134">Installare le definizioni dei criteri da [Microsoft Edge for Business](https://www.microsoft.com/edge/business/download).</span><span class="sxs-lookup"><span data-stu-id="36b5d-134">Install the Policy Definitions from [Microsoft Edge for Business](https://www.microsoft.com/edge/business/download).</span></span>

   - <span data-ttu-id="36b5d-135">Selezionare il canale, la build e la piattaforma da usare e quindi fare clic sull'opzione per scaricare i file dei criteri.</span><span class="sxs-lookup"><span data-stu-id="36b5d-135">Pick the CHANNEL/BUILD and PLATFORM you want to use, and then click GET POLICY FILES.</span></span>
   - <span data-ttu-id="36b5d-136">Estrarre i file compressi.</span><span class="sxs-lookup"><span data-stu-id="36b5d-136">Extract the zipped files.</span></span>
   - <span data-ttu-id="36b5d-137">Copia msedge.admx e msedgeupdate.admx nella directory `C:\Windows\PolicyDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="36b5d-137">Copy msedge.admx and msedgeupdate.admx to the `C:\Windows\PolicyDefinitions` directory.</span></span>
   - <span data-ttu-id="36b5d-138">Copiare msedge.adml and msedgeupdate.adml (dalla directory della lingua/delle impostazioni locali appropriata) alla directory `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]`.</span><span class="sxs-lookup"><span data-stu-id="36b5d-138">Copy msedge.adml and msedgeupdate.adml (from the appropriate language/locale directory) to the `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` directory.</span></span>

2. <span data-ttu-id="36b5d-139">Apri l'editor Criteri di gruppo (gpedit.msc).</span><span class="sxs-lookup"><span data-stu-id="36b5d-139">Open the Group Policy Editor (gpedit.msc).</span></span>
3. <span data-ttu-id="36b5d-140">In **Configurazione computer** vai a *Modelli amministrativi > Microsoft Edge Update > Applicazioni*.</span><span class="sxs-lookup"><span data-stu-id="36b5d-140">Under **Computer Configuration**, go to *Administrative Templates>Microsoft Edge Update>Applications*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36b5d-141">Se la cartella *Microsoft Edge Update* non è visualizzata, verificare che il passaggio 1 sia stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="36b5d-141">If you don't see the *Microsoft Edge Update* folder, verify that step 1 was completed correctly.</span></span>

4. <span data-ttu-id="36b5d-142">In **Applicazioni** fai doppio clic su "Consenti esperienza browser Microsoft Edge affiancata".</span><span class="sxs-lookup"><span data-stu-id="36b5d-142">Under **Applications**, double-click "Allow Microsoft Edge Side by Side browser experience".</span></span> <span data-ttu-id="36b5d-143">Vedi le nostre [indicazioni sulle procedure consigliate](#best-practice-guidance) prima di continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="36b5d-143">See our [best practice guidance](#best-practice-guidance) before continuing to the next step.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36b5d-144">Per impostazione predefinita, questo criterio di gruppo è impostato su "Non configurato", il che comporta la scomparsa di Microsoft Edge Legacy quando viene installata la nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-144">By default, this group policy is set to "Not configured", which results in Microsoft Edge Legacy being hidden when the new version of Microsoft Edge is installed.</span></span>

5. <span data-ttu-id="36b5d-145">Seleziona **Abilitato**, quindi scegli **OK**.</span><span class="sxs-lookup"><span data-stu-id="36b5d-145">Select **Enabled** and then click **OK**.</span></span>  

<span data-ttu-id="36b5d-146">Abilitando questo criterio, la chiave del Registro di sistema seguente verrà impostata su' 00000001':</span><span class="sxs-lookup"><span data-stu-id="36b5d-146">Setting this policy will set the following Registry Key  to '00000001':</span></span>

- <span data-ttu-id="36b5d-147">Chiave:</span><span class="sxs-lookup"><span data-stu-id="36b5d-147">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- <span data-ttu-id="36b5d-148">Nome:</span><span class="sxs-lookup"><span data-stu-id="36b5d-148">Value Name:</span></span> `Allowsxs`
- <span data-ttu-id="36b5d-149">Tipo valore:</span><span class="sxs-lookup"><span data-stu-id="36b5d-149">Value Type:</span></span> `'REG_DWORD'`

#### <span data-ttu-id="36b5d-150">Indicazioni sulle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="36b5d-150">Best practice guidance</span></span>

<span data-ttu-id="36b5d-151">Per un'esperienza ottimale, il criterio **Consenti esperienza browser Microsoft Edge affiancata** dovrà essere abilitato prima che la nuova versione di Microsoft Edge sia distribuita nei dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="36b5d-151">For the best experience, the **Allow Microsoft Edge Side by Side browser experience** should be enabled before the new version of Microsoft Edge is deployed to your users' devices.</span></span>

<span data-ttu-id="36b5d-152">Se i criteri di gruppo vengono abilitati dopo la distribuzione di Microsoft Edge, sono presenti gli effetti collaterali e le azioni necessarie seguenti:</span><span class="sxs-lookup"><span data-stu-id="36b5d-152">If the group policy is enabled after Microsoft Edge is deployed, there are the following side effects and required actions:</span></span>

1. <span data-ttu-id="36b5d-153">**Consenti esperienza browser Microsoft Edge affiancata** non avrà effetto finché non verrà eseguito di nuovo il programma di installazione per la nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-153">**Allow Microsoft Edge Side by Side browser experience** won't take effect until after the installer for the new version of Microsoft Edge is run again.</span></span>

   > [!NOTE]
   > <span data-ttu-id="36b5d-154">Il programma di installazione può essere eseguito direttamente o automaticamente quando viene aggiornata la nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-154">The installer can be run directly or automatically when the new version of Microsoft Edge updates.</span></span>

2. <span data-ttu-id="36b5d-155">Microsoft Edge Legacy dovrà essere aggiunto di nuovo a Start o alla Barra delle applicazioni perché la migrazione della scelta viene eseguita quando viene distribuita la nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-155">Microsoft Edge Legacy will need to be re-pinned to Start or the Taskbar because the pin is migrated when the new version of Microsoft Edge is deployed.</span></span>
3. <span data-ttu-id="36b5d-156">I siti aggiunti a Start o alla Barra delle applicazioni per Microsoft Edge Legacy verranno migrati alla nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-156">Sites that were pinned to Start or the Taskbar for Microsoft Edge Legacy will be migrated to the new version of Microsoft Edge.</span></span>

## <span data-ttu-id="36b5d-157">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="36b5d-157">Additional information</span></span>

<span data-ttu-id="36b5d-158">Dopo che i sistemi sono stati completamente aggiornati e viene installato il canale Stable della versione successiva di Microsoft Edge, viene impostata la seguente chiave del registro di sistema con relativo valore:</span><span class="sxs-lookup"><span data-stu-id="36b5d-158">After the systems are fully updated and the Stable channel of the next version of Microsoft Edge is installed, the following registry key and value is set:</span></span>

- <span data-ttu-id="36b5d-159">Chiave:</span><span class="sxs-lookup"><span data-stu-id="36b5d-159">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- <span data-ttu-id="36b5d-160">Valore chiave:</span><span class="sxs-lookup"><span data-stu-id="36b5d-160">Key value:</span></span> `BrowserReplacement`

  > [!IMPORTANT]
  > <span data-ttu-id="36b5d-161">Questa chiave è sovrascritta ogni volta che viene aggiornato il canale Microsoft Edge Stable.</span><span class="sxs-lookup"><span data-stu-id="36b5d-161">This key is over-written every time the Microsoft Edge Stable channel is updated.</span></span> <span data-ttu-id="36b5d-162">Come procedura consigliata, ti suggeriamo di NON eliminare questa chiave per consentire agli utenti di accedere a entrambe le versioni di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="36b5d-162">As a best practice, we recommend that you DO NOT delete this key to allow users to access both versions of Microsoft Edge.</span></span>

## <span data-ttu-id="36b5d-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36b5d-163">See also</span></span>

- [<span data-ttu-id="36b5d-164">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="36b5d-164">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="36b5d-165">Aggiornamenti di Windows per supportare Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36b5d-165">Windows updates to support Microsoft Edge</span></span>](microsoft-edge-sysupdate-windows-updates.md)
