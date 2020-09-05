---
title: Rollback di Microsoft Edge per le aziende
ms.author: v-danwes
author: dan-wesley
manager: srugh
ms.date: 09/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Come eseguire il rollback di Microsoft Edge a una versione precedente
ms.openlocfilehash: 9f659b0bcdd82f54a814c8ad4157521061cdfa7c
ms.sourcegitcommit: 827a47d641c7ddc1d89be5d5fc0615373dec18b0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993706"
---
# <span data-ttu-id="0d9fb-103">Come eseguire il rollback di Microsoft Edge a una versione precedente</span><span class="sxs-lookup"><span data-stu-id="0d9fb-103">How to roll back Microsoft Edge to a previous version</span></span>

<span data-ttu-id="0d9fb-104">Questo articolo descrive come eseguire il rollback a una versione precedente di Microsoft Edge usando la funzionalità di rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-104">This article describes how to roll back to a previous version of Microsoft Edge using the rollback feature.</span></span>

>[!NOTE]
><span data-ttu-id="0d9fb-105">Questo articolo si applica a Microsoft Edge versione 86 o successiva.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="0d9fb-106">Introduzione al rollback</span><span class="sxs-lookup"><span data-stu-id="0d9fb-106">Introduction to rollback</span></span>

<span data-ttu-id="0d9fb-107">Il rollback consente di sostituire la versione corrente del browser Microsoft Edge con una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-107">Rollback lets you replace your Microsoft Edge browser version with an earlier version.</span></span> <span data-ttu-id="0d9fb-108">Questa funzionalità è stata sviluppata per fungere da rete di protezione per le aziende che distribuiscono Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-108">This feature is designed to be a safety net for enterprises deploying Microsoft Edge.</span></span> <span data-ttu-id="0d9fb-109">Consente di risolvere problemi relativi a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-109">It provides a way to troubleshoot issues with Microsoft Edge.</span></span> <span data-ttu-id="0d9fb-110">Uno dei vantaggi del rollback è la possibilità di tornare alla versione precedente del browser in modo semplice e rapido.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-110">The benefits of rollback are the ability to revert to previous browser version easily and quickly.</span></span> <span data-ttu-id="0d9fb-111">Il rollback riduce l’impatto potenziale di un problema di Microsoft Edge sulle operazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-111">Rollback reduces the potential impact that a Microsoft Edge issue has on business operations.</span></span>

## <span data-ttu-id="0d9fb-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0d9fb-112">Before you begin</span></span>

<span data-ttu-id="0d9fb-113">È importante comprendere come avviene l’installazione della funzionalità di rollback in un ambiente Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-113">It's important to understand how the rollback feature is installed in a Microsoft Edge environment.</span></span> <span data-ttu-id="0d9fb-114">È possibile distribuire il rollback in due modi diversi: manualmente con un MSI o usando Microsoft Edge Update e Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-114">You can deploy rollback using two different methods: manually with an MSI or by using Microsoft Edge update and Group Policy.</span></span> <span data-ttu-id="0d9fb-115">È anche consigliabile usare determinati Criteri di gruppo per una distribuzione più fluida.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-115">We also  encourage using a selection of Group Policies for a smoother deployment.</span></span>

### <span data-ttu-id="0d9fb-116">Consigli</span><span class="sxs-lookup"><span data-stu-id="0d9fb-116">Recommendations</span></span>

<span data-ttu-id="0d9fb-117">La funzionalità di rollback è pensata come correzione temporanea per i problemi che potrebbe causare un aggiornamento del browser Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-117">The rollback feature is meant to be a temporary fix for issues you might find in a Microsoft Edge browser update.</span></span> <span data-ttu-id="0d9fb-118">È consigliabile installare l’ultima versione del browser Microsoft Edge per sfruttare la protezione fornita dagli aggiornamenti della sicurezza più recenti.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-118">We recommend that users install the latest version of the Microsoft Edge browser to use the protection provided by the latest security updates.</span></span> <span data-ttu-id="0d9fb-119">Il ripristino di una versione precedente può comportare rischi di esposizione a problemi di sicurezza noti.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-119">Rollback to an earlier version risks exposure to known security issues.</span></span>

<span data-ttu-id="0d9fb-120">Prima di ripristinare temporaneamente la versione precedente del browser, è inoltre consigliabile abilitare la sincronizzazione per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-120">Before temporarily rolling back your browser version, we also highly recommend that you enable Sync for all the users in your organization.</span></span> <span data-ttu-id="0d9fb-121">Se la sincronizzazione non viene abilitata, si rischia la perdita permanente dei dati di navigazione.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-121">If you don't turn on Sync, there's a risk of permanent browsing data loss.</span></span> <span data-ttu-id="0d9fb-122">Per altre informazioni sulla sincronizzazione, vedere [Sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-122">For more information about Sync, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="0d9fb-123">Usare il rollback solo se necessario, in quanto comporta sempre un rischio di perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-123">Only use rollback when necessary, there's always the risk of data loss.</span></span>

## <span data-ttu-id="0d9fb-124">Abilitare manualmente il rollback con un MSI</span><span class="sxs-lookup"><span data-stu-id="0d9fb-124">Enable rollback manually with an MSI</span></span>

<span data-ttu-id="0d9fb-125">Seguire la procedura seguente per eseguire il rollback manualmente con un MSI.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-125">Use the following steps to roll back manually with an MSI.</span></span>

1. <span data-ttu-id="0d9fb-126">Disabilitare Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-126">Disable Microsoft Edge Updates.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0d9fb-127">È consigliabile installare i Modelli amministrativi più recenti.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-127">We recommend that you install the most current Administrative templates.</span></span> <span data-ttu-id="0d9fb-128">Per ulteriori informazioni, vedere [Scaricare e installare il modello amministrativo di Microsoft Edge](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-128">For more information, see [Download and install the Microsoft Edge administrative template](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template).</span></span>

   - <span data-ttu-id="0d9fb-129">Aprire l'Editor Criteri di gruppo locali e passare a *Configurazione computer>Modelli amministrativi>Microsoft Edge Update>Applicazioni>Microsoft Edge>*.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-129">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
   - <span data-ttu-id="0d9fb-130">Selezionare **Sostituzione dei criteri di aggiornamento** e quindi selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-130">Select **Update policy override** and then select **Enabled**.</span></span>
   - <span data-ttu-id="0d9fb-131">In **Opzioni** scegliere **Aggiornamento disabilitato** nell'elenco a discesa Criteri.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-131">Under **Options**, pick **Update disabled** from the Policy dropdown list.</span></span>

2. <span data-ttu-id="0d9fb-132">Ottenere il file MSI.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-132">Get the MSI.</span></span>

   - <span data-ttu-id="0d9fb-133">Scaricare [da qui](https://www.microsoft.com/edge/business/download) il file MSI per la versione di cui si vuole eseguire il rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-133">Download the MSI for the version you want to roll back to [from here](https://www.microsoft.com/edge/business/download).</span></span>
   - <span data-ttu-id="0d9fb-134">Salvare il file MSI nel desktop.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-134">Save the MSI to your desktop.</span></span>

3. <span data-ttu-id="0d9fb-135">Eseguire il comando di rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-135">Run the rollback command.</span></span>

   - <span data-ttu-id="0d9fb-136">Aprire il prompt dei comandi di Windows con **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-136">Open the Windows command prompt with **Run as administrator**.</span></span>
   - <span data-ttu-id="0d9fb-137">Digitare il comando seguente, dove: *C:\Users\username\Desktop\test* rappresenta il percorso del file MSI scaricato e FileName è il nome del file MSI:</span><span class="sxs-lookup"><span data-stu-id="0d9fb-137">Type the following command, where: *C:\Users\username\Desktop\test* is the path to the MSI you downloaded, and FileName is the name of the .msi file:</span></span><br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > <span data-ttu-id="0d9fb-138">Per altre informazioni su msiexec, vedere [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-138">For more information about msiexec, see [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).</span></span>
   - <span data-ttu-id="0d9fb-139">Chiudere e riaprire Microsoft Edge per verificare che il rollback sia andato a buon fine.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-139">Close and reopen Microsoft Edge to verify that the rollback worked.</span></span> <span data-ttu-id="0d9fb-140">In **Impostazioni e altro** (ALT + F), passare a **Impostazioni** e selezionare **Informazioni su Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-140">Under **Settings and more** (ALT + F), go to **Settings** and select **About Microsoft Edge**.</span></span>

## <span data-ttu-id="0d9fb-141">Abilitare il rollback con Microsoft Edge Update e Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d9fb-141">Enable rollback with Microsoft Edge update and Group Policy</span></span>

<span data-ttu-id="0d9fb-142">Seguire la procedura seguente per abilitare il rollback con Microsoft Edge Update e Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-142">Use the following steps to enable rollback with Microsoft Edge update and Group Policy.</span></span>

1. <span data-ttu-id="0d9fb-143">Aprire l'Editor Criteri di gruppo locali e passare a *Configurazione computer>Modelli amministrativi>Microsoft Edge Update>Applicazioni>Microsoft Edge>*.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-143">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
2. <span data-ttu-id="0d9fb-144">Selezionare **Ripristina versione di destinazione** e quindi selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-144">Select **Rollback to target version** and then select **Enabled**.</span></span>
3. <span data-ttu-id="0d9fb-145">Selezionare **Sostituzione della versione di destinazione** e scegliere la versione del browser di cui si vuole eseguire il rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-145">Select **Target version override** and pick the browser version you want to roll back to.</span></span>
4. <span data-ttu-id="0d9fb-146">Selezionare **Sostituzione dei criteri di aggiornamento** e quindi selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-146">Select **Update policy override** and then select **Enabled**.</span></span> <span data-ttu-id="0d9fb-147">In **Opzioni**, selezionare una delle opzioni seguenti nell'elenco a discesa Criteri (tranne **Aggiornamento disabilitato**):</span><span class="sxs-lookup"><span data-stu-id="0d9fb-147">Under **Options**, pick one of the following options from the Policy dropdown list (except for **Update disabled**):</span></span>

   - <span data-ttu-id="0d9fb-148">Consenti sempre gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="0d9fb-148">Always allow updates</span></span>
   - <span data-ttu-id="0d9fb-149">Solo aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="0d9fb-149">Automatic silent updates only</span></span>

     > [!NOTE]
     > <span data-ttu-id="0d9fb-150">Per forzare un aggiornamento dei criteri di gruppo, digitare `dsregcmd /status` nel prompt dei comandi di Windows (Esegui come amministratore).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-150">To force a group policy update, type `dsregcmd /status` at the Windows administrator Command Prompt (Run as administrator).</span></span>

5. <span data-ttu-id="0d9fb-151">Fai clic su **OK** per salvare le impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-151">Click **OK** to save the policy settings.</span></span> <span data-ttu-id="0d9fb-152">Il rollback verrà eseguito la volta successiva in cui Microsoft Edge Update verificherà la presenza di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-152">Rollback will happen the next time Microsoft Edge Update checks for an update.</span></span> <span data-ttu-id="0d9fb-153">Se si vuole eseguire prima l'aggiornamento, è necessario modificare l'intervallo di polling di Microsoft Edge Update o abilitare il rollback con un MSI.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-153">If you want the update to happen sooner, you can change the Microsoft Edge Update polling interval or enable rollback using an MSI.</span></span>

### <span data-ttu-id="0d9fb-154">Errori comuni di rollback</span><span class="sxs-lookup"><span data-stu-id="0d9fb-154">Common rollback errors</span></span>

<span data-ttu-id="0d9fb-155">Gli errori seguenti impediscono l’esecuzione del rollback:</span><span class="sxs-lookup"><span data-stu-id="0d9fb-155">The following errors will prevent rollback:</span></span>

- <span data-ttu-id="0d9fb-156">L’input è una versione di destinazione non supportata</span><span class="sxs-lookup"><span data-stu-id="0d9fb-156">Input is an unsupported target version</span></span>
- <span data-ttu-id="0d9fb-157">L’input è una versione di destinazione inesistente</span><span class="sxs-lookup"><span data-stu-id="0d9fb-157">Input is a non-existent target version</span></span>
- <span data-ttu-id="0d9fb-158">L’input è formattato in modo errato</span><span class="sxs-lookup"><span data-stu-id="0d9fb-158">Input is incorrectly formatted</span></span>

### <span data-ttu-id="0d9fb-159">Criteri di gruppo consigliati</span><span class="sxs-lookup"><span data-stu-id="0d9fb-159">Recommended Group Policies</span></span>

<span data-ttu-id="0d9fb-160">Le impostazioni e i criteri di gruppo seguenti sono altamente consigliati per eseguire il rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-160">The following group policies and settings are highly recommended for using rollback.</span></span>

#### <span data-ttu-id="0d9fb-161">Criteri di gruppo per la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="0d9fb-161">Sync Group Policies</span></span>

- <span data-ttu-id="0d9fb-162">ForceSync.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-162">ForceSync.</span></span> <span data-ttu-id="0d9fb-163">Impostare ForceSync su Abilitato.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-163">Set ForceSync to enabled.</span></span> <span data-ttu-id="0d9fb-164">Questo criterio impone l'abilitazione della sincronizzazione per tutti gli utenti di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-164">This policy will force enable Sync on all Azure Active Directory (Azure AD) users.</span></span> <span data-ttu-id="0d9fb-165">Questo criterio è valido solo per la versione 86 di Microsoft Edge e le versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-165">This policy is only effective for Microsoft Edge versions 86 and later.</span></span>
- <span data-ttu-id="0d9fb-166">*Configura l'elenco dei tipi esclusi dai criteri di sincronizzazione* consente agli amministratori di controllare i dati che possono essere sincronizzati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-166">The *Configure the list of the types that are excluded from synchronization policy* allows admins to control what data can be synced by users.</span></span>

#### <span data-ttu-id="0d9fb-167">Criteri di gruppo di riavvio del browser</span><span class="sxs-lookup"><span data-stu-id="0d9fb-167">Browser restart Group Policies</span></span>

<span data-ttu-id="0d9fb-168">È consigliabile imporre agli utenti il riavvio dopo l'abilitazione del rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-168">We recommend forcing a restart on users after rollback is enabled.</span></span>

- <span data-ttu-id="0d9fb-169">Abilitare *Invia una notifica a un utente in merito al riavvio del browser consigliato o necessario per gli aggiornamenti in sospeso*.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-169">Enable *Notify a user that a browser restart is recommended or required for pending updates*.</span></span> <span data-ttu-id="0d9fb-170">In Opzioni selezionare **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-170">Under Options, select **Required**.</span></span>
- <span data-ttu-id="0d9fb-171">Abilitare *Imposta il periodo di tempo per le notifiche sugli aggiornamenti* e quindi impostare l'ora desiderata in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-171">Enable *Set the time period for update notifications* and then set the desired time in milliseconds.</span></span>

## <span data-ttu-id="0d9fb-172">Snapshot</span><span class="sxs-lookup"><span data-stu-id="0d9fb-172">Snapshot</span></span>

<span data-ttu-id="0d9fb-173">Una snapshot è una copia con versione stampata della cartella dei dati dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-173">A snapshot is a version stamped copy of the user data folder.</span></span> <span data-ttu-id="0d9fb-174">Durante un aggiornamento della versione, una snapshot della versione precedente viene creata e salvata nella cartella della snapshot.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-174">During a version upgrade, a snapshot of the previous version is made and stored in the snapshot folder.</span></span> <span data-ttu-id="0d9fb-175">Al termine del rollback, una snapshot con versione corrispondente sarà copiata nella nuova cartella di dati dell'utente e cancellata dalla cartella della snapshot.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-175">After rollback occurs, a version matched snapshot will be copied into the new user data folder and deleted from the snapshot folder.</span></span> <span data-ttu-id="0d9fb-176">Se nessuna snapshot con versione corrispondente è disponibile dopo il downgrade, il rollback utilizzerà Sync per immettere i dati dell'utente nella nuova versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-176">If no version matched snapshot is available upon downgrade, rollback will rely on Sync to populate user data into the new Microsoft Edge version.</span></span>

<span data-ttu-id="0d9fb-177">Il criterio di gruppo [UserDataSnapshotRetentionLimit] consente di definire un limite per il numero di snapshot che possono essere conservate in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-177">The [UserDataSnapshotRetentionLimit] group policy allows you to set a limit for the number of snapshots that can be retained at any given time.</span></span> <span data-ttu-id="0d9fb-178">Per impostazione predefinita, vengono conservate tre snapshot.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-178">By default, three snapshots are kept.</span></span> <span data-ttu-id="0d9fb-179">Il criterio può essere configurato per conservare da 0 a 5 snapshot.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-179">You can configure this policy to keep from 0-5 snapshots.</span></span>

## <span data-ttu-id="0d9fb-180">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="0d9fb-180">Frequently asked questions</span></span>

### <span data-ttu-id="0d9fb-181">Rollback manuale con MSI</span><span class="sxs-lookup"><span data-stu-id="0d9fb-181">Manual MSI rollback</span></span>

#### <span data-ttu-id="0d9fb-182">Quali errori generici di MSI possono verificarsi?</span><span class="sxs-lookup"><span data-stu-id="0d9fb-182">What generic MSI failures that can happen?</span></span>

1. <span data-ttu-id="0d9fb-183">Se il criterio di gruppo Installa aggiornamento è disabilitato, non verrà eseguito il rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-183">If the Install update group policy is disabled, rollback won't occur.</span></span>

   - <span data-ttu-id="0d9fb-184">Per eseguire il rollback, assicurarsi che l'opzione Installa sia impostata su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-184">To use rollback, make sure Install is set to **Enabled**.</span></span> <span data-ttu-id="0d9fb-185">Se questo criterio è disabilitato, i canali di Microsoft Edge non possono essere installati.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-185">When this policy is disabled, it prevents Microsoft Edge channels from being installed.</span></span> <span data-ttu-id="0d9fb-186">Per ulteriori informazioni, vedere [Installa](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-186">For more information, see [Install](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install).</span></span>

2. <span data-ttu-id="0d9fb-187">Se gli aggiornamenti di riconoscimento dei dati aziendali non sono presenti, le installazioni di Microsoft Edge verranno bloccate, a meno che non sia abilitato *Consenti esperienza browser Microsoft Edge affiancata*.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-187">If Enlightenment Updates aren't present, Microsoft Edge installations will be blocked unless *Allow Microsoft Edge Side by Side browser experience* is enabled.</span></span>

   - <span data-ttu-id="0d9fb-188">Per Windows versioni 1903 e 1909: se l'ultimo aggiornamento è precedente a ottobre 2019, potrebbe verificarsi questo problema.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-188">For Windows versions 1903 and 1909: If your last update was before October 2019, you may have this issue.</span></span>
   - <span data-ttu-id="0d9fb-189">Per Windows versioni 1709, 1803 e 1809: se l'ultimo aggiornamento è precedente a novembre 2019, potrebbe verificarsi questo problema.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-189">For Windows versions 1709, 1803, and 1809: If your last update was before November 2019, you may have this issue.</span></span><br>
<span data-ttu-id="0d9fb-190">Per altre informazioni, vedere [Aggiornamenti di Windows per supportare la prossima versione di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)</span><span class="sxs-lookup"><span data-stu-id="0d9fb-190">For more information, see [Windows updates to support the next version of Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)</span></span>

#### <span data-ttu-id="0d9fb-191">È apparso il messaggio di errore seguente dopo che ho usato il prompt dei comandi e il rollback non si è verificato.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-191">The following error message was shown after using the Command Prompt and rollback didn't occur.</span></span> <span data-ttu-id="0d9fb-192">Qual è il problema?</span><span class="sxs-lookup"><span data-stu-id="0d9fb-192">What's wrong?</span></span>

![Messaggio di stato del rollback](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

<span data-ttu-id="0d9fb-194">*ALLOWDOWNGRADE=1* non è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-194">*ALLOWDOWNGRADE=1* was not executed.</span></span>

### <span data-ttu-id="0d9fb-195">Rollback con Microsoft Edge Update e Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d9fb-195">Microsoft Edge Update and Group Policy rollback</span></span>

#### <span data-ttu-id="0d9fb-196">Ho impostato *Ripristina versione di destinazione*, abilitato *Sostituzione dei criteri di aggiornamento*, immesso la versione del browser desiderata per *Sostituzione della versione di destinazione*, ma la versione del browser non era quella prevista.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-196">I set *Rollback to target version*, enabled *Update policy override*, input my desired browser version for *Target version override*, but the browser version wasn't what I expected.</span></span> <span data-ttu-id="0d9fb-197">Qual è il problema?</span><span class="sxs-lookup"><span data-stu-id="0d9fb-197">What's wrong?</span></span>

<span data-ttu-id="0d9fb-198">Alcuni errori comuni che impediscono l’esecuzione del rollback sono:</span><span class="sxs-lookup"><span data-stu-id="0d9fb-198">Some common errors that prevent rollback are:</span></span>

- <span data-ttu-id="0d9fb-199">Se Ripristina versione di destinazione non è impostato, il rollback non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-199">If Rollback to target version isn't set, rollback will not be executed.</span></span>
- <span data-ttu-id="0d9fb-200">L'impostazione di sostituzione della versione di destinazione presenta uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d9fb-200">There are one of the following issues with the target version override setting:</span></span>

  - <span data-ttu-id="0d9fb-201">La sostituzione della versione di destinazione è impostata su una versione di destinazione non supportata.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-201">Target version override is set to an unsupported target version.</span></span>
  - <span data-ttu-id="0d9fb-202">La sostituzione della versione di destinazione è impostata su una versione di destinazione inesistente.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-202">Target version override is set to a non-existent target version.</span></span>
  - <span data-ttu-id="0d9fb-203">L'input della sostituzione della versione di destinazione è formattato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-203">Target version override input is incorrectly formatted.</span></span>

- <span data-ttu-id="0d9fb-204">Se Sostituzione dei criteri di aggiornamento è impostato su "Aggiornamenti disabilitati", Microsoft Edge Update non accetterà alcun aggiornamento e il rollback non sarà eseguito.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-204">If Update policy override is set to "Updates disabled", Microsoft Edge Update won't accept any updates and rollback isn't executed.</span></span>

### <span data-ttu-id="0d9fb-205">Ho impostato correttamente tutti i criteri di gruppo, ma il rollback non è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-205">I set all the group policies correctly, but rollback didn't execute.</span></span> <span data-ttu-id="0d9fb-206">Cosa è successo?</span><span class="sxs-lookup"><span data-stu-id="0d9fb-206">What happened?</span></span>

<span data-ttu-id="0d9fb-207">Microsoft Edge Update non ha ancora verificato la disponibilità di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-207">Microsoft Edge Update hasn't run a check for updates yet.</span></span> <span data-ttu-id="0d9fb-208">Per impostazione predefinita, l'aggiornamento automatico verifica la disponibilità degli aggiornamenti ogni 10 ore.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-208">By default, auto-update checks for updates every 10 hours.</span></span> <span data-ttu-id="0d9fb-209">Per risolvere il problema, è possibile modificare l'intervallo di polling di Microsoft Edge Update con il criterio di gruppo Sostituzione del periodo di controllo dell'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-209">You can fix this issue by changing Microsoft Edge Update's polling interval with the Auto-update check period override group policy.</span></span> <span data-ttu-id="0d9fb-210">Per altre informazioni, vedere il criterio [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-210">For more information, see the [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) policy.</span></span>

### <span data-ttu-id="0d9fb-211">In quanto amministratore IT, ho eseguito correttamente i passaggi per il rollback.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-211">As an IT admin, I followed all the steps for rollback correctly.</span></span> <span data-ttu-id="0d9fb-212">Il rollback è stato eseguito solo per una parte del mio gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-212">Only a portion of my user group was rolled back.</span></span> <span data-ttu-id="0d9fb-213">Perché per gli altri utenti non è ancora avvenuto?</span><span class="sxs-lookup"><span data-stu-id="0d9fb-213">Why haven't the other users been rolled back yet?</span></span>

<span data-ttu-id="0d9fb-214">L'impostazione dei criteri di gruppo non è ancora stata sincronizzata con tutti i client.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-214">The group policy setting hasn't synced to all the clients yet.</span></span> <span data-ttu-id="0d9fb-215">Quando gli amministratori configurano un criterio di gruppo, i client non ricevono le nuove impostazioni immediatamente.</span><span class="sxs-lookup"><span data-stu-id="0d9fb-215">When admins set a group policy, clients don't receive these settings instantaneously.</span></span> <span data-ttu-id="0d9fb-216">È possibile [Forzare un aggiornamento remoto di Criteri di gruppo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="0d9fb-216">You can [Force a Remote Group Policy Refresh](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11)).</span></span>


## <span data-ttu-id="0d9fb-217">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d9fb-217">See also</span></span>

- [<span data-ttu-id="0d9fb-218">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="0d9fb-218">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
