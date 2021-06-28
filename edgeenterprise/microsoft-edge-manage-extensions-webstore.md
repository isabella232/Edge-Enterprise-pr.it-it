---
title: Estensioni Microsoft Edge per test interno
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 04/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Informazioni su come creare pacchetti e estensioni di Microsoft Edge per test interno nell'organizzazione.
ms.openlocfilehash: 403b6879b15c146f40fa2564da76eae59b2abe88
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618158"
---
# <a name="self-host-microsoft-edge-extensions"></a><span data-ttu-id="a4c74-103">Estensioni Microsoft Edge per test interno</span><span class="sxs-lookup"><span data-stu-id="a4c74-103">Self-host Microsoft Edge extensions</span></span>

<span data-ttu-id="a4c74-104">Questo articolo fornisce indicazioni di base per creare un pacchetto di un'estensione da ospitare nel tuo negozio web.</span><span class="sxs-lookup"><span data-stu-id="a4c74-104">This article provides basic guidance for packaging an extension to host on your own webstore.</span></span> <span data-ttu-id="a4c74-105">Include inoltre istruzioni su come distribuire le estensioni ai dispositivi e agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-105">It also includes instructions on how to deploy extensions to devices and users in your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4c74-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a4c74-106">Prerequisites</span></span>

<span data-ttu-id="a4c74-107">Per ospitare autonomamente le proprie estensioni, è necessario fornire servizi di hosting Web personalizzati per le estensioni e i relativi file manifesto.</span><span class="sxs-lookup"><span data-stu-id="a4c74-107">To self-host your own extensions, you will need to provide your own web hosting services for the extensions and their manifest files.</span></span>

 <span data-ttu-id="a4c74-108">I passaggi seguenti presuppongono che tu abbia già creato l'estensione, abbia esperienza con i file XML, abbia una conoscenza approfondita della configurazione di criteri di gruppo e sappia come usare il Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="a4c74-108">The following steps assume that you’ve already created your extension, have some experience with XML files, have a working knowledge of configuring group policy, and know how to use the Windows registry.</span></span>

## <a name="publish-an-extension"></a><span data-ttu-id="a4c74-109">Pubblicare un'estensione</span><span class="sxs-lookup"><span data-stu-id="a4c74-109">Publish an extension</span></span>

<span data-ttu-id="a4c74-110">Prima di pubblicare un'estensione, è necessario comprimerla in un file CRX (estensione Chrome).</span><span class="sxs-lookup"><span data-stu-id="a4c74-110">Before you publish an extension it needs to be packed into a CRX (Chrome extension) file.</span></span> <span data-ttu-id="a4c74-111">Usa la procedura seguente come guida per la creazione di un pacchetto di un'estensione come file CRX.</span><span class="sxs-lookup"><span data-stu-id="a4c74-111">Use the following steps as a guide to packing an extension as a CRX file.</span></span>

1. <span data-ttu-id="a4c74-112">Nella barra Microsoft Edge indirizzo, vai a *edge://extensions* e attiva **la modalità sviluppatore** se non è già abilitata.</span><span class="sxs-lookup"><span data-stu-id="a4c74-112">In the Microsoft Edge address bar, go to *edge://extensions* and turn on **Developer mode** if it’s not already enabled.</span></span>
2. <span data-ttu-id="a4c74-113">In **Estensioni installate**fare clic su **Comprimi estensione** per creare il file CRX.</span><span class="sxs-lookup"><span data-stu-id="a4c74-113">Under **Installed extensions**, click **Pack Extension** to create the CRX file.</span></span>
3. <span data-ttu-id="a4c74-114">Usa la finestra di dialogo **Comprimi estensione** per trovare la directory con l'origine per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-114">Use the **Pack extension** dialog to find the directory that has the source for the extension.</span></span> <span data-ttu-id="a4c74-115">Selezionare la directory e quindi fare clic su **Comprimi estensione**.</span><span class="sxs-lookup"><span data-stu-id="a4c74-115">Select the directory and then click **Pack extension**.</span></span>  <span data-ttu-id="a4c74-116">Verrà creato il file CRX, insieme a un file PEM.</span><span class="sxs-lookup"><span data-stu-id="a4c74-116">This will create your CRX file, along with a PEM file.</span></span> <span data-ttu-id="a4c74-117">Salvare il file PEM perché è necessario per apportare aggiornamenti della versione dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-117">Save the PEM file because it’s needed for making version updates to the extension.</span></span> <span data-ttu-id="a4c74-118">La schermata successiva mostra la finestra di dialogo **Comprimi estensione** per l'individuazione della directory radice dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-118">The next screenshot shows the **Pack extension** dialog for locating the root directory of the extension.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="Finestra di dialogo di comprimi estensione per trovare il codice sorgente di un'estensione.":::

   > [!IMPORTANT]
   > <span data-ttu-id="a4c74-120">Archiviare il file PEM in un percorso sicuro perché è la chiave per l'estensione ed è necessario per gli aggiornamenti futuri.</span><span class="sxs-lookup"><span data-stu-id="a4c74-120">Store the PEM file in a safe location because it’s the key for the extension and it’s needed for future updates.</span></span>

4. <span data-ttu-id="a4c74-121">Trascinare il file CRX nella finestra delle estensioni e assicurati che sia caricato.</span><span class="sxs-lookup"><span data-stu-id="a4c74-121">Drag the CRX file into your extensions window and make sure that it loads.</span></span>
5. <span data-ttu-id="a4c74-122">Testare l'estensione e prendere nota del campo ID (questo è l'ID CRX) e del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-122">Test the extension and take note of the ID field (this is the CRX ID) and version number.</span></span> <span data-ttu-id="a4c74-123">Queste informazioni saranno necessarie in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a4c74-123">You’ll need this information later.</span></span> <span data-ttu-id="a4c74-124">La schermata successiva mostra un'estensione di test con il relativo ID CRX.</span><span class="sxs-lookup"><span data-stu-id="a4c74-124">The next screenshot shows a test extension with its CRX ID.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="Esempio di estensione che mostra l'ID CRX":::

6. <span data-ttu-id="a4c74-126">Upload il file CRX nell'host e prendere nota dell'URL del percorso da cui verrà scaricato.</span><span class="sxs-lookup"><span data-stu-id="a4c74-126">Upload the the CRX file to the host and note the URL of the location it will be downloaded from.</span></span> <span data-ttu-id="a4c74-127">Queste informazioni sono necessarie per il file manifesto XML.</span><span class="sxs-lookup"><span data-stu-id="a4c74-127">This information is needed for the XML manifest file.</span></span>
7. <span data-ttu-id="a4c74-128">Per creare un file XML manifesto con l'ID app/estensione, l'URL di download e la versione, definisci i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4c74-128">To create a manifest XML file with the app/extension ID, download URL, and version, define the following fields:</span></span>  

   - <span data-ttu-id="a4c74-129">**appid** - ID dell’estensione del passaggio 5</span><span class="sxs-lookup"><span data-stu-id="a4c74-129">**appid** - The extension ID from step 5</span></span>
   - <span data-ttu-id="a4c74-130">**codebase** - Percorso di download per il file CRX del passaggio 6</span><span class="sxs-lookup"><span data-stu-id="a4c74-130">**codebase** - The download location for the CRX file from step 6</span></span>
   - <span data-ttu-id="a4c74-131">**version** - Versione dell'app/estensione, che deve corrispondere alla versione specificata nel manifesto dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-131">**version** - The version of the app/extension, which should match the version specified in the manifest of the extension.</span></span>

   <span data-ttu-id="a4c74-132">Il frammento di codice successivo mostra un esempio di file manifesto XML.</span><span class="sxs-lookup"><span data-stu-id="a4c74-132">The next code snippet shows an example of an XML manifest file.</span></span>

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   <span data-ttu-id="a4c74-133">Per ulteriori informazioni, vedere [Aggiornamento automatico delle estensioni in Microsoft Edge - Sviluppo di Microsoft Edge](/microsoft-edge/extensions-chromium/enterprise/auto-update).</span><span class="sxs-lookup"><span data-stu-id="a4c74-133">For more information, see [Auto-update extensions in Microsoft Edge - Microsoft Edge Development](/microsoft-edge/extensions-chromium/enterprise/auto-update).</span></span>

8. <span data-ttu-id="a4c74-134">Caricare il file XML completato in un percorso da cui è possibile scaricarlo, prendendo nota dell'URL.</span><span class="sxs-lookup"><span data-stu-id="a4c74-134">Upload the completed XML file to a location where it can be downloaded from, noting the URL.</span></span> <span data-ttu-id="a4c74-135">Questo URL sarà necessario quando installi l'estensione usando criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a4c74-135">This URL will be needed when you install the extension using a group policy.</span></span> <span data-ttu-id="a4c74-136">Vedere [Distribuire un'estensione ospitata privatamente.](#distribute-a-privately-hosted-extension)</span><span class="sxs-lookup"><span data-stu-id="a4c74-136">See [Distribute a privately hosted extension](#distribute-a-privately-hosted-extension).</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a4c74-137">Il percorso di hosting per l'estensione non richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-137">The hosting location for the extension doesn’t need authentication.</span></span> <span data-ttu-id="a4c74-138">Deve essere accessibile dai dispositivi degli utenti da ovunque possa essere usata.</span><span class="sxs-lookup"><span data-stu-id="a4c74-138">It needs to be accessible by user devices wherever they might be used.</span></span>

## <a name="publish-updates-to-an-extension"></a><span data-ttu-id="a4c74-139">Pubblicare aggiornamenti in un'estensione</span><span class="sxs-lookup"><span data-stu-id="a4c74-139">Publish updates to an extension</span></span>

<span data-ttu-id="a4c74-140">Dopo aver modificato e testato l'estensione aggiornata, ė possibile pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="a4c74-140">After you change and test the updated extension you can publish it.</span></span> <span data-ttu-id="a4c74-141">Utilizzare la procedura seguente come guida per la pubblicazione di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a4c74-141">Use the following steps as a guide for publishing an update.</span></span>

1. <span data-ttu-id="a4c74-142">Modificare il numero di versione nel file manifest.JSON dell'estensione in un numero superiore utilizzando la sintassi seguente: `"version":"versionString"`.</span><span class="sxs-lookup"><span data-stu-id="a4c74-142">Change the version number in your extension's manifest.JSON file to a higher number using the following syntax: `"version":"versionString"`.</span></span> <span data-ttu-id="a4c74-143">Se ė la "versione":"1.0", puoi eseguire l'aggiornamento a "version":"1.1" o a qualsiasi numero superiore a "1.0".</span><span class="sxs-lookup"><span data-stu-id="a4c74-143">If the "version":"1.0", then you can update to "version":"1.1" or any number higher than "1.0".</span></span>
2. <span data-ttu-id="a4c74-144">Aggiornare la "versione" di `<updatecheck>` nel file XML in modo che corrisponda al numero inserito nel file manifesto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="a4c74-144">Update the "version" of `<updatecheck>` in the XML file to match the number that you put in the manifest file in the previous step.</span></span> <span data-ttu-id="a4c74-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a4c74-145">For example:</span></span><br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. <span data-ttu-id="a4c74-146">Crea un file CRX che include le nuove modifiche.</span><span class="sxs-lookup"><span data-stu-id="a4c74-146">Create a CRX file that includes the new changes.</span></span> <span data-ttu-id="a4c74-147">Passare a *edge://extensions* e abilitare la **modalità sviluppatore**.</span><span class="sxs-lookup"><span data-stu-id="a4c74-147">Go to *edge://extensions* and enable **Developer mode**.</span></span>
4. <span data-ttu-id="a4c74-148">Fare clic su **Comprimi estensione** e passare alla directory per l'origine dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-148">Click **Pack extension** and go to the directory for the extension source.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a4c74-149">Utilizzare lo stesso file PEM generato e salvato la prima volta che è stato creato il file CRX.</span><span class="sxs-lookup"><span data-stu-id="a4c74-149">Use the same PEM file that was generated and saved the first time the CRX file was created.</span></span> <span data-ttu-id="a4c74-150">Se non si usa lo stesso file PEM, l'ID app dell'estensione verrà modificato e l'aggiornamento verrà considerato come una nuova estensione.</span><span class="sxs-lookup"><span data-stu-id="a4c74-150">If you don't use the same PEM file the app ID of the extension will change and the update will be treated as a new extension.</span></span>

5. <span data-ttu-id="a4c74-151">Trascinare il file CRX nella finestra delle estensioni e verificare che sia caricato.</span><span class="sxs-lookup"><span data-stu-id="a4c74-151">Drag and drop the CRX file into the extensions window and verify that it loads.</span></span>
6. <span data-ttu-id="a4c74-152">Testare l'estensione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="a4c74-152">Test the updated extension.</span></span>
7. <span data-ttu-id="a4c74-153">Sostituire il vecchio file CRX e il file XML con i nuovi file per l'estensione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="a4c74-153">Replace the old CRX file and XML file with the new files for the updated extension.</span></span>

<span data-ttu-id="a4c74-154">Le modifiche dell'estensione verranno ritirate durante il successivo ciclo di sincronizzazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="a4c74-154">The extension's changes will be picked up during the next policy sync cycle.</span></span> <span data-ttu-id="a4c74-155">Per ulteriori informazioni sull'aggiornamento delle estensioni, vedere: [aggiornamento URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) e [aggiornamento manifesto](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest).</span><span class="sxs-lookup"><span data-stu-id="a4c74-155">For more information about updating extensions, see: [Update URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) and [Update manifest](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest).</span></span>

## <a name="distribute-a-privately-hosted-extension"></a><span data-ttu-id="a4c74-156">Distribuire un'estensione ospitata privatamente</span><span class="sxs-lookup"><span data-stu-id="a4c74-156">Distribute a privately hosted extension</span></span>

<span data-ttu-id="a4c74-157">Puoi condividere il collegamento del percorso in cui è ospitato il file CRX e non appena gli utenti immettono l'URL nel browser, l'estensione verrà scaricata e installata.</span><span class="sxs-lookup"><span data-stu-id="a4c74-157">You can share the link of the location where the CRX file is hosted, and as soon as users enter the URL in their browser the extension will be downloaded and installed.</span></span> <span data-ttu-id="a4c74-158">Gli utenti possono abilitare l'estensione dalla pagina edge://extensions.</span><span class="sxs-lookup"><span data-stu-id="a4c74-158">Users can enable the extension from the edge://extensions page.</span></span> <span data-ttu-id="a4c74-159">Per consentire agli utenti di installare estensioni ospitate privatamente, devi aggiungere gli ID CRX di estensione al criterio [ExtensionInstallAllowList.](/deployedge/microsoft-edge-policies#extensioninstallallowlist)</span><span class="sxs-lookup"><span data-stu-id="a4c74-159">To allow users to install self-hosted extensions, you need to add the extension CRX IDs to the [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) policy.</span></span>

<span data-ttu-id="a4c74-160">In alternativa, puoi usare i criteri di gruppo [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) per forzare l'installazione di un'estensione nei dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a4c74-160">Alternatively, you can use group policy [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) to Force-install an extension on your users’ devices.</span></span>

<span data-ttu-id="a4c74-161">Puoi applicare questi criteri agli utenti selezionati, ai dispositivi o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="a4c74-161">You can apply these policies to your selected users, devices, or both.</span></span> <span data-ttu-id="a4c74-162">Tenere presente che gli aggiornamenti dei criteri non sono istantanei e che passerà del tempo prima che le impostazioni dei criteri saranno effettive.</span><span class="sxs-lookup"><span data-stu-id="a4c74-162">Remember though that policy updates are not instantaneous, and it will take time for the policy settings to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4c74-163">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a4c74-163">See also</span></span>

- [<span data-ttu-id="a4c74-164">Gestire le estensioni di Microsoft Edge nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a4c74-164">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="a4c74-165">Usare i criteri di gruppo per gestire le estensioni di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a4c74-165">Use group policies to manage Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-policies.md)
- [<span data-ttu-id="a4c74-166">Guida dettagliata al criterio ExtensionSettings</span><span class="sxs-lookup"><span data-stu-id="a4c74-166">Detailed guide to the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="a4c74-167">Domande frequenti sulle estensioni di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a4c74-167">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="a4c74-168">Pagina di destinazione di Microsoft Edge per le aziende</span><span class="sxs-lookup"><span data-stu-id="a4c74-168">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
