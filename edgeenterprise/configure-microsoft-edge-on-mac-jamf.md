---
title: Configurare Microsoft Edge in macOS con Jamf
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge nei dispositivi Mac con Jamf
ms.openlocfilehash: 336bdfed2c53811615b0183dc5ca7db916cd7428
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980128"
---
# <span data-ttu-id="81d78-103">Configurare le impostazioni dei criteri di Microsoft Edge in macOS con Jamf</span><span class="sxs-lookup"><span data-stu-id="81d78-103">Configure Microsoft Edge policy settings on macOS with Jamf</span></span>

<span data-ttu-id="81d78-104">Questo articolo descrive come configurare le impostazioni dei criteri in macOS usando un file manifesto dei criteri Microsoft Edge in Jamf Pro 10.19.</span><span class="sxs-lookup"><span data-stu-id="81d78-104">This article describes how to configure policy settings on macOS using a Microsoft Edge policy manifest file on Jamf Pro 10.19.</span></span>

<span data-ttu-id="81d78-105">È possibile anche configurare le impostazioni dei criteri di Microsoft Edge su macOS usando un file di elenco delle proprietà (.plist).</span><span class="sxs-lookup"><span data-stu-id="81d78-105">You can also configure Microsoft Edge policy settings on macOS by using a property list (.plist) file.</span></span> <span data-ttu-id="81d78-106">Per altre informazioni, consultare [Configurare macOS con un file plist](configure-microsoft-edge-on-mac.md)</span><span class="sxs-lookup"><span data-stu-id="81d78-106">For more information, see [Configure for macOS using a .plist](configure-microsoft-edge-on-mac.md)</span></span>


## <span data-ttu-id="81d78-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="81d78-107">Prerequisites</span></span>

<span data-ttu-id="81d78-108">È necessario il software seguente:</span><span class="sxs-lookup"><span data-stu-id="81d78-108">The following software is required:</span></span>

- <span data-ttu-id="81d78-109">Canale Stable di Microsoft Edge 81</span><span class="sxs-lookup"><span data-stu-id="81d78-109">Microsoft Edge Stable channel 81</span></span>
- <span data-ttu-id="81d78-110">File dei modelli di criteri, versione 81.0.416.3</span><span class="sxs-lookup"><span data-stu-id="81d78-110">Policy Templates file, version 81.0.416.3</span></span>
- <span data-ttu-id="81d78-111">Jamf Pro, versione 10.19</span><span class="sxs-lookup"><span data-stu-id="81d78-111">Jamf Pro, Version 10.19</span></span>

## <span data-ttu-id="81d78-112">Informazioni sul menu Impostazioni dell'applicazione e personalizzate di Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="81d78-112">About the Jamf Pro Application & Custom Settings menu</span></span>

<span data-ttu-id="81d78-113">Prima di Jamf Pro 10,18, era necessario creare manualmente un file plist per la gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="81d78-113">Before Jamf Pro 10.18, managing Office 365 involved manually building a .plist file.</span></span> <span data-ttu-id="81d78-114">Si trattava di un flusso di lavoro che richiedeva molto tempo e una solida preparazione tecnica.</span><span class="sxs-lookup"><span data-stu-id="81d78-114">This was a time-consuming workflow that required a strong technical background.</span></span> <span data-ttu-id="81d78-115">Jamf Pro 10.18 ha superato tali ostacoli semplificando il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="81d78-115">Jamf Pro 10.18 eliminated those barriers by streamlining the configuration process.</span></span> <span data-ttu-id="81d78-116">Tuttavia, gli amministratori IT possono usare questa nuova interfaccia utente solo per determinate applicazioni e domini di preferenza specificati da Jamf.</span><span class="sxs-lookup"><span data-stu-id="81d78-116">However, IT Admins could only use this new user interface for specific applications and preference domains specified by Jamf.</span></span>

<span data-ttu-id="81d78-117">In Jamf Pro 10.19 l'utente può caricare un manifesto JSON come "schema personalizzato" scegliendo qualsiasi dominio di preferenza come destinazione, l'interfaccia utente grafica verrà generata da tale manifesto.</span><span class="sxs-lookup"><span data-stu-id="81d78-117">In Jamf Pro 10.19, a user can upload a JSON manifest as a "custom schema" to target any preference domain, and the graphical user interface will be generated from this manifest.</span></span> <span data-ttu-id="81d78-118">Lo schema personalizzato creato segue la specifica dello Schema JSON.</span><span class="sxs-lookup"><span data-stu-id="81d78-118">The custom schema that's created follows the JSON Schema specification.</span></span>

<span data-ttu-id="81d78-119">Per altre informazioni, consultare [Profili di configurazione del computer](https://jamf.it/computer-configuration-profiles) nel manuale dell'amministratore di Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="81d78-119">For more information, see [Computer Configuration Profiles](https://jamf.it/computer-configuration-profiles) in the Jamf Pro Administrator's Guide.</span></span>

## <span data-ttu-id="81d78-120">Ottenere il manifesto dei criteri per una versione specifica di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="81d78-120">Get the policy manifest for a specific version of Microsoft Edge</span></span>

<span data-ttu-id="81d78-121">Per ottenere il manifesto del criterio:</span><span class="sxs-lookup"><span data-stu-id="81d78-121">To get the policy manifest:</span></span>

- <span data-ttu-id="81d78-122">Passare alla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise).</span><span class="sxs-lookup"><span data-stu-id="81d78-122">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="81d78-123">Nell'elenco a discesa Canale/Versione, selezionare \*\*qualsiasi canale con la versione 81 o successiva.\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="81d78-123">On the Channel/Version dropdown list, select \*\*any channel with version 81 or later.\*\*\*.</span></span>
- <span data-ttu-id="81d78-124">Nell'elenco a discesa Build selezionare qualsiasi \*\*Build 81 o versione successiva.\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="81d78-124">On the Build dropdown list, select any \*\*81 build or later.\*\*\*.</span></span>
- <span data-ttu-id="81d78-125">Fare clic su OTTIENI FILE DEI CRITERI per scaricare il pacchetto dei modelli di criteri.</span><span class="sxs-lookup"><span data-stu-id="81d78-125">Click GET POLICY FILES to download our policy templates bundle.</span></span>

  > [!NOTE]
  > <span data-ttu-id="81d78-126">Attualmente il pacchetto dei modelli di criteri è firmato come file CAB.</span><span class="sxs-lookup"><span data-stu-id="81d78-126">Currently, the policy templates bundle is signed as a CAB file.</span></span> <span data-ttu-id="81d78-127">È necessario usare uno strumento di terze parti, ad esempio The Unarchiver per aprire il file in macOS.</span><span class="sxs-lookup"><span data-stu-id="81d78-127">You'll need to use a 3rd party tool, such as The Unarchiver to open the file on macOS.</span></span>

<span data-ttu-id="81d78-128">Decomprimere prima il file CAB poi il file ZIP e passare alla directory "Mac" di primo livello.</span><span class="sxs-lookup"><span data-stu-id="81d78-128">After you unpack the CAB file, unpack the ZIP file and navigate to the "mac" top level directory.</span></span> <span data-ttu-id="81d78-129">Il manifesto, denominato "policy_manifest.json, si trova in questa directory.</span><span class="sxs-lookup"><span data-stu-id="81d78-129">The manifest, which is named "policy_manifest.json", is in this directory.</span></span>

<span data-ttu-id="81d78-130">Questo manifesto verrà pubblicato in ogni pacchetto di criteri a partire dalla build 81.0.416.3.</span><span class="sxs-lookup"><span data-stu-id="81d78-130">This manifest will be published in every policy bundle starting with build 81.0.416.3.</span></span> <span data-ttu-id="81d78-131">Se si vogliono testare i criteri nel canale Dev, è possibile usare il manifesto associato a ogni rilascio di Dev e testarlo in Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="81d78-131">If you want to test policies in the Dev channel, you can take the manifest associated with each Dev release and test it in Jamf Pro.</span></span>  

## <span data-ttu-id="81d78-132">Usare il manifesto dei criteri in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="81d78-132">Use the policy manifest in Jamf Pro</span></span>

<span data-ttu-id="81d78-133">Seguire la procedura seguente per caricare il manifesto dei criteri in Jamf Pro e poi creare un profilo dei criteri per macOS.</span><span class="sxs-lookup"><span data-stu-id="81d78-133">Use the following steps to upload the policy manifest to Jamf Pro and then create a policy profile for macOS.</span></span>

1. <span data-ttu-id="81d78-134">Accedere a Jamf.</span><span class="sxs-lookup"><span data-stu-id="81d78-134">Sign in to Jamf.</span></span>
2. <span data-ttu-id="81d78-135">Selezionare la scheda **Computer**.</span><span class="sxs-lookup"><span data-stu-id="81d78-135">Select the **Computer** tab.</span></span>
3. <span data-ttu-id="81d78-136">In **Gestione dei contenuti** selezionare **Profili di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="81d78-136">Under **Content Management**, select **Configuration Profiles**.</span></span>
4. <span data-ttu-id="81d78-137">Nella pagina **Profili di configurazione** fare clic su **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="81d78-137">On the **Configuration Profiles** page, click **+ New**.</span></span>

   ![Aggiungere un nuovo profilo in Jamf](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. <span data-ttu-id="81d78-139">In **Nuovo profilo di configurazione di macOS**>**Opzioni** selezionare \*\* Impostazioni dell'applicazione e personalizzate\*\*.</span><span class="sxs-lookup"><span data-stu-id="81d78-139">On **New macOS Configuration Profile**>**Options**, select **Application & Custom Settings**.</span></span>
6. <span data-ttu-id="81d78-140">Nella finestra popup **Impostazioni dell'applicazione e personalizzate** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="81d78-140">On the **Application & Custom Settings** popup window, click **Configure**.</span></span>

   ![Configurare le impostazioni dell'applicazione e le impostazioni personalizzate](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. <span data-ttu-id="81d78-142">Nella sezione **Impostazioni dell'applicazione e personalizzate** impostare i valori visualizzati nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="81d78-142">In the **Application & Custom Settings** section, set the values shown in the following screen shot.</span></span>

   ![Origine profilo e schema personalizzato](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - <span data-ttu-id="81d78-144">Per **Metodo di creazione** selezionare **Configura le impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="81d78-144">For **Creation Method**, pick **Configure settings**.</span></span>
   - <span data-ttu-id="81d78-145">Per **Origine** selezionare **Schema personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="81d78-145">For **Source**, pick **Custom Schema**.</span></span>
   - <span data-ttu-id="81d78-146">Per **Dominio di preferenza** specificare il nome del proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="81d78-146">For **Preference Domain**, provide the name of your domain.</span></span> <span data-ttu-id="81d78-147">Questo esempio usa *com.microsoft.Edge* come dominio.</span><span class="sxs-lookup"><span data-stu-id="81d78-147">This example uses *com.microsoft.Edge* as the domain.</span></span>
   - <span data-ttu-id="81d78-148">Per **Schema personalizzato** incollare il contenuto del file manifesto "policy_manifest.json".</span><span class="sxs-lookup"><span data-stu-id="81d78-148">For **Custom Schema**, paste the contents of the "policy_manifest.json" manifest file.</span></span>
   - <span data-ttu-id="81d78-149">Fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="81d78-149">Click **Save**.</span></span>

8. <span data-ttu-id="81d78-150">Dopo aver salvato il profilo, Jamf visualizza la sezione **Generale** mostrata nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="81d78-150">After you save the profile, Jamf displays the **General** section shown in the next screen shot.</span></span>

   ![Configurare la Sezione generale](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - <span data-ttu-id="81d78-152">Fornire un **Nome** visualizzato per il profilo e una **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="81d78-152">Provide a display **Name** for the profile and a **Description**.</span></span>
   - <span data-ttu-id="81d78-153">Mantenere l'impostazione predefinita per la **Categoria** ovvero **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="81d78-153">Keep the default setting for **Category**, which is **None**.</span></span>
   - <span data-ttu-id="81d78-154">Per **Metodo di distribuzione** le opzioni sono **Installa automaticamente** oppure **Rendi disponibile in modalità self-service**.</span><span class="sxs-lookup"><span data-stu-id="81d78-154">For **Distribution Method**, the options are **Install Automatically** or **Make Available in Self Service**.</span></span>
   - <span data-ttu-id="81d78-155">Per **Livello** le opzioni sono **Livello utente** o **Livello computer**.</span><span class="sxs-lookup"><span data-stu-id="81d78-155">For **Level**, the options are **User Level** or **Computer Level**.</span></span>
   - <span data-ttu-id="81d78-156">Fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="81d78-156">Click **Save**.</span></span>

9. <span data-ttu-id="81d78-157">Dopo aver salvato la Sezione generale, Jamf visualizza il profilo di configurazione del canale Microsoft Edge Beta impostato per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="81d78-157">After you save the General section, Jamf shows the "Microsoft Edge Beta Channel" configuration profile set up for our example.</span></span> <span data-ttu-id="81d78-158">Nella schermata successiva, tenere presente che è possibile continuare a usare il profilo facendo clic **Modifica** oppure, se si è terminato, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="81d78-158">In the next screen shot, note that you can keep working the profile by clicking **Edit** or if you're finished, click **Done**.</span></span>

   ![Nuovo profilo di configurazione con opzioni](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > <span data-ttu-id="81d78-160">È possibile modificare il profilo dopo che è stato salvato e in un'altra sessione di Jamf.</span><span class="sxs-lookup"><span data-stu-id="81d78-160">You can edit this profile after it's been saved and in another Jamf session.</span></span> <span data-ttu-id="81d78-161">Ad esempio, si può decidere di modificare il metodo di distribuzione per renderla disponibile in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="81d78-161">For example, you might decide to change the Distribution Method to Make Available in Self Service.</span></span>

   <span data-ttu-id="81d78-162">Per eseguire una successiva modifica al canale Stable di Microsoft Edge o per eliminarlo, selezionare il nome del profilo visualizzato nella schermata Profili di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="81d78-162">To do a follow up edit on the Microsoft Edge Stable Channel, or delete it, select the profile name, shown in the following Configuration Profiles screen shot.</span></span>

   ![Elenco profili di configurazione](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

<span data-ttu-id="81d78-164">Dopo aver creato il nuovo profilo di configurazione, è necessario configurare l'**Ambito** per il profilo.</span><span class="sxs-lookup"><span data-stu-id="81d78-164">After you create the new configuration profile you still have to configure the **Scope** for the profile.</span></span>

### <span data-ttu-id="81d78-165">Per configurare l'ambito</span><span class="sxs-lookup"><span data-stu-id="81d78-165">To configure the scope</span></span>

1. <span data-ttu-id="81d78-166">Per **Destinazioni** specificare le impostazioni minime seguenti:</span><span class="sxs-lookup"><span data-stu-id="81d78-166">For **Targets**, provide the following minimum settings:</span></span>

   - <span data-ttu-id="81d78-167">COMPUTER DI DESTINAZIONE.</span><span class="sxs-lookup"><span data-stu-id="81d78-167">TARGET COMPUTERS.</span></span> <span data-ttu-id="81d78-168">Le opzioni disponibili sono: computer specifici o tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="81d78-168">The options are Specific Computers or All Computers.</span></span>
   - <span data-ttu-id="81d78-169">UTENTI DI DESTINAZIONE.</span><span class="sxs-lookup"><span data-stu-id="81d78-169">TARGET USERS.</span></span> <span data-ttu-id="81d78-170">Le opzioni disponibili sono: utenti specifici o tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="81d78-170">The options are Specific Users or All Users.</span></span>
   - <span data-ttu-id="81d78-171">Fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="81d78-171">Click **Save**.</span></span>
2. <span data-ttu-id="81d78-172">Per **Limitazioni** mantenere l'impostazione predefinita: Nessuna.</span><span class="sxs-lookup"><span data-stu-id="81d78-172">For **Limitations**, keep the default setting: None.</span></span> <span data-ttu-id="81d78-173">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="81d78-173">Click **Cancel**.</span></span>
3. <span data-ttu-id="81d78-174">Per **Esclusioni** mantenere l'impostazione predefinita: Nessuna.</span><span class="sxs-lookup"><span data-stu-id="81d78-174">For **Exclusions**, keep the default setting: None.</span></span> <span data-ttu-id="81d78-175">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="81d78-175">Click **Cancel**.</span></span>

## <span data-ttu-id="81d78-176">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="81d78-176">Frequently Asked Questions</span></span>

### <span data-ttu-id="81d78-177">Microsoft Edge può essere configurato per l'uso delle preferenze master?</span><span class="sxs-lookup"><span data-stu-id="81d78-177">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="81d78-178">Sì, Microsoft Edge può essere configurato per l'uso di un file delle preferenze master.</span><span class="sxs-lookup"><span data-stu-id="81d78-178">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

<span data-ttu-id="81d78-179">Un file delle preferenze master consente di configurare le impostazioni predefinite per un profilo utente del browser quando Microsoft Edge viene distribuito.</span><span class="sxs-lookup"><span data-stu-id="81d78-179">A master preferences file lets you configure default settings for a browser user profile when Microsoft Edge is deployed.</span></span> <span data-ttu-id="81d78-180">Puoi anche usare un file delle preferenze master per applicare le impostazioni nei computer che non sono gestiti da un sistema di gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="81d78-180">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="81d78-181">Queste impostazioni vengono applicate al profilo dell'utente la prima volta che l'utente usa il browser.</span><span class="sxs-lookup"><span data-stu-id="81d78-181">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="81d78-182">Dopo che l'utente ha usato il browser, le modifiche apportate al file delle preferenze master non vengono applicate.</span><span class="sxs-lookup"><span data-stu-id="81d78-182">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="81d78-183">Un utente può modificare le impostazioni delle preferenze master nel browser.</span><span class="sxs-lookup"><span data-stu-id="81d78-183">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="81d78-184">Se desideri impostare un valore obbligatorio o modificare un'impostazione dopo la prima esecuzione del browser, devi usare un criterio.</span><span class="sxs-lookup"><span data-stu-id="81d78-184">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="81d78-185">Un file delle preferenze master ti permette di personalizzare molte impostazioni e preferenze diverse per il browser, incluse quelle condivise con altri browser basati su Chromium e specifici per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="81d78-185">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="81d78-186">Le preferenze relative ai criteri possono essere configurate usando il file delle preferenze master.</span><span class="sxs-lookup"><span data-stu-id="81d78-186">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="81d78-187">Nei casi in cui è stato impostato un criterio ed è presente un set di preferenze master corrispondente, l'impostazione dei criteri ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="81d78-187">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81d78-188">Tutte le preferenze disponibili potrebbero non essere coerenti con la terminologia e le convenzioni di denominazione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="81d78-188">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="81d78-189">Non c'è alcuna garanzia che queste preferenze continueranno a funzionare come previsto nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="81d78-189">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="81d78-190">Le preferenze potrebbero essere modificate o ignorate nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="81d78-190">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="81d78-191">Un file delle preferenze master è un file di testo formattato con il markup JSON.</span><span class="sxs-lookup"><span data-stu-id="81d78-191">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="81d78-192">Questo file deve essere aggiunto alla stessa directory dell'eseguibile msedge.exe.</span><span class="sxs-lookup"><span data-stu-id="81d78-192">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="81d78-193">Per distribuzioni aziendali a livello di sistema in macOS si tratta in genere di "*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" o "*/Library/Microsoft/Microsoft Edge Master Preferences*".</span><span class="sxs-lookup"><span data-stu-id="81d78-193">For system wide enterprise deployments on macOS this is typically: “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" or "*/Library/Microsoft/Microsoft Edge Master Preferences*”.</span></span>

## <span data-ttu-id="81d78-194">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="81d78-194">See also</span></span>

- [<span data-ttu-id="81d78-195">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="81d78-195">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="81d78-196">Configurare per macOS con Intune</span><span class="sxs-lookup"><span data-stu-id="81d78-196">Configure for macOS with Intune</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="81d78-197">Configurare per Windows</span><span class="sxs-lookup"><span data-stu-id="81d78-197">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="81d78-198">Configurare per Windows con Intune</span><span class="sxs-lookup"><span data-stu-id="81d78-198">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
