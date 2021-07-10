---
title: Configurare Microsoft Edge in macOS con Jamf
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 6/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge nei dispositivi Mac con Jamf
ms.openlocfilehash: 8556a5b1d0fc01feb67fc86cb016a9ed47061b55
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641632"
---
# <a name="configure-microsoft-edge-policy-settings-on-macos-with-jamf"></a><span data-ttu-id="9c9bd-103">Configurare le impostazioni dei criteri di Microsoft Edge in macOS con Jamf</span><span class="sxs-lookup"><span data-stu-id="9c9bd-103">Configure Microsoft Edge policy settings on macOS with Jamf</span></span>

<span data-ttu-id="9c9bd-104">Questo articolo descrive come configurare le impostazioni dei criteri in macOS usando un file manifesto dei criteri Microsoft Edge in Jamf Pro 10.19.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-104">This article describes how to configure policy settings on macOS using a Microsoft Edge policy manifest file on Jamf Pro 10.19.</span></span>

<span data-ttu-id="9c9bd-105">È possibile anche configurare le impostazioni dei criteri di Microsoft Edge su macOS usando un file di elenco delle proprietà (.plist).</span><span class="sxs-lookup"><span data-stu-id="9c9bd-105">You can also configure Microsoft Edge policy settings on macOS by using a property list (.plist) file.</span></span> <span data-ttu-id="9c9bd-106">Per altre informazioni, consultare [Configurare macOS con un file plist](configure-microsoft-edge-on-mac.md)</span><span class="sxs-lookup"><span data-stu-id="9c9bd-106">For more information, see [Configure for macOS using a .plist](configure-microsoft-edge-on-mac.md)</span></span>


## <a name="prerequisites"></a><span data-ttu-id="9c9bd-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9c9bd-107">Prerequisites</span></span>

<span data-ttu-id="9c9bd-108">È necessario il software seguente:</span><span class="sxs-lookup"><span data-stu-id="9c9bd-108">The following software is required:</span></span>

- <span data-ttu-id="9c9bd-109">Canale Stable di Microsoft Edge 81</span><span class="sxs-lookup"><span data-stu-id="9c9bd-109">Microsoft Edge Stable channel 81</span></span>
- <span data-ttu-id="9c9bd-110">File dei modelli di criteri, versione 81.0.416.3</span><span class="sxs-lookup"><span data-stu-id="9c9bd-110">Policy Templates file, version 81.0.416.3</span></span>
- <span data-ttu-id="9c9bd-111">Jamf Pro, versione 10.19</span><span class="sxs-lookup"><span data-stu-id="9c9bd-111">Jamf Pro, Version 10.19</span></span>

## <a name="about-the-jamf-pro-application--custom-settings-menu"></a><span data-ttu-id="9c9bd-112">Informazioni sul menu Impostazioni dell'applicazione e personalizzate di Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="9c9bd-112">About the Jamf Pro Application & Custom Settings menu</span></span>

<span data-ttu-id="9c9bd-113">Prima di Jamf Pro 10,18, era necessario creare manualmente un file plist per la gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-113">Before Jamf Pro 10.18, managing Office 365 involved manually building a .plist file.</span></span> <span data-ttu-id="9c9bd-114">Si trattava di un flusso di lavoro che richiedeva molto tempo e una solida preparazione tecnica.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-114">This was a time-consuming workflow that required a strong technical background.</span></span> <span data-ttu-id="9c9bd-115">Jamf Pro 10.18 ha superato tali ostacoli semplificando il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-115">Jamf Pro 10.18 eliminated those barriers by streamlining the configuration process.</span></span> <span data-ttu-id="9c9bd-116">Tuttavia, gli amministratori IT possono usare questa nuova interfaccia utente solo per determinate applicazioni e domini di preferenza specificati da Jamf.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-116">However, IT Admins could only use this new user interface for specific applications and preference domains specified by Jamf.</span></span>

<span data-ttu-id="9c9bd-117">In Jamf Pro 10.19 l'utente può caricare un manifesto JSON come "schema personalizzato" scegliendo qualsiasi dominio di preferenza come destinazione, l'interfaccia utente grafica verrà generata da tale manifesto.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-117">In Jamf Pro 10.19, a user can upload a JSON manifest as a "custom schema" to target any preference domain, and the graphical user interface will be generated from this manifest.</span></span> <span data-ttu-id="9c9bd-118">Lo schema personalizzato creato segue la specifica dello Schema JSON.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-118">The custom schema that's created follows the JSON Schema specification.</span></span>

<span data-ttu-id="9c9bd-119">Per altre informazioni, consultare [Profili di configurazione del computer](https://jamf.it/computer-configuration-profiles) nel manuale dell'amministratore di Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-119">For more information, see [Computer Configuration Profiles](https://jamf.it/computer-configuration-profiles) in the Jamf Pro Administrator's Guide.</span></span>

## <a name="get-the-policy-manifest-for-a-specific-version-of-microsoft-edge"></a><span data-ttu-id="9c9bd-120">Ottenere il manifesto dei criteri per una versione specifica di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9c9bd-120">Get the policy manifest for a specific version of Microsoft Edge</span></span>

<span data-ttu-id="9c9bd-121">Per ottenere il manifesto del criterio:</span><span class="sxs-lookup"><span data-stu-id="9c9bd-121">To get the policy manifest:</span></span>

- <span data-ttu-id="9c9bd-122">Passare alla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise).</span><span class="sxs-lookup"><span data-stu-id="9c9bd-122">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="9c9bd-123">Nell'elenco a discesa Canale/versione selezionare **un canale qualsiasi con la versione 81 o successiva.**_.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-123">On the Channel/Version dropdown list, select **any channel with version 81 or later.**_.</span></span>
- <span data-ttu-id="9c9bd-124">Nell'elenco a discesa Build, selezionare qualsiasi _ \*build 81 o successiva.\*\*_</span><span class="sxs-lookup"><span data-stu-id="9c9bd-124">On the Build dropdown list, select any _*81 build or later.*\*_.</span></span>
- <span data-ttu-id="9c9bd-125">Fare clic su OTTIENI FILE DEI CRITERI per scaricare il pacchetto dei modelli di criteri.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-125">Click GET POLICY FILES to download our policy templates bundle.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9c9bd-126">Attualmente il pacchetto dei modelli di criteri è firmato come file CAB.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-126">Currently, the policy templates bundle is signed as a CAB file.</span></span> <span data-ttu-id="9c9bd-127">È necessario usare uno strumento di terze parti, ad esempio The Unarchiver per aprire il file in macOS.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-127">You'll need to use a 3rd party tool, such as The Unarchiver to open the file on macOS.</span></span>

<span data-ttu-id="9c9bd-128">Decomprimere prima il file CAB poi il file ZIP e passare alla directory "Mac" di primo livello.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-128">After you unpack the CAB file, unpack the ZIP file and navigate to the "mac" top level directory.</span></span> <span data-ttu-id="9c9bd-129">Il manifesto, denominato "policy_manifest.json, si trova in questa directory.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-129">The manifest, which is named "policy_manifest.json", is in this directory.</span></span>

<span data-ttu-id="9c9bd-130">Questo manifesto verrà pubblicato in ogni pacchetto di criteri a partire dalla build 81.0.416.3.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-130">This manifest will be published in every policy bundle starting with build 81.0.416.3.</span></span> <span data-ttu-id="9c9bd-131">Se si vogliono testare i criteri nel canale Dev, è possibile usare il manifesto associato a ogni rilascio di Dev e testarlo in Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-131">If you want to test policies in the Dev channel, you can take the manifest associated with each Dev release and test it in Jamf Pro.</span></span>  

## <a name="use-the-policy-manifest-in-jamf-pro"></a><span data-ttu-id="9c9bd-132">Usare il manifesto dei criteri in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="9c9bd-132">Use the policy manifest in Jamf Pro</span></span>

<span data-ttu-id="9c9bd-133">Seguire la procedura seguente per caricare il manifesto dei criteri in Jamf Pro e poi creare un profilo dei criteri per macOS.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-133">Use the following steps to upload the policy manifest to Jamf Pro and then create a policy profile for macOS.</span></span>

1. <span data-ttu-id="9c9bd-134">Accedere a Jamf.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-134">Sign in to Jamf.</span></span>
2. <span data-ttu-id="9c9bd-135">Selezionare la scheda _\*Computer\*\*.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-135">Select the _*Computer*\* tab.</span></span>
3. <span data-ttu-id="9c9bd-136">In **Gestione dei contenuti** selezionare **Profili di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-136">Under **Content Management**, select **Configuration Profiles**.</span></span>
4. <span data-ttu-id="9c9bd-137">Nella pagina **Profili di configurazione** fare clic su **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-137">On the **Configuration Profiles** page, click **+ New**.</span></span>

   ![Aggiungere un nuovo profilo in Jamf](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. <span data-ttu-id="9c9bd-139">In **Nuovo profilo di configurazione di macOS**>**Opzioni** selezionare \*\* Impostazioni dell'applicazione e personalizzate\*\*.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-139">On **New macOS Configuration Profile**>**Options**, select **Application & Custom Settings**.</span></span>
6. <span data-ttu-id="9c9bd-140">Nella finestra popup **Impostazioni dell'applicazione e personalizzate** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-140">On the **Application & Custom Settings** popup window, click **Configure**.</span></span>

   ![Configurare le impostazioni dell'applicazione e le impostazioni personalizzate](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. <span data-ttu-id="9c9bd-142">Nella sezione **Impostazioni dell'applicazione e personalizzate** impostare i valori visualizzati nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-142">In the **Application & Custom Settings** section, set the values shown in the following screen shot.</span></span>

   ![Origine profilo e schema personalizzato](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - <span data-ttu-id="9c9bd-144">Per **Metodo di creazione** selezionare **Configura le impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-144">For **Creation Method**, pick **Configure settings**.</span></span>
   - <span data-ttu-id="9c9bd-145">Per **Origine** selezionare **Schema personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-145">For **Source**, pick **Custom Schema**.</span></span>
   - <span data-ttu-id="9c9bd-146">Per **Dominio di preferenza** specificare il nome del proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-146">For **Preference Domain**, provide the name of your domain.</span></span> <span data-ttu-id="9c9bd-147">Questo esempio usa *com.microsoft.Edge* come dominio.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-147">This example uses *com.microsoft.Edge* as the domain.</span></span>
   - <span data-ttu-id="9c9bd-148">Per **Schema personalizzato** incollare il contenuto del file manifesto "policy_manifest.json".</span><span class="sxs-lookup"><span data-stu-id="9c9bd-148">For **Custom Schema**, paste the contents of the "policy_manifest.json" manifest file.</span></span>
   - <span data-ttu-id="9c9bd-149">Fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-149">Click **Save**.</span></span>

8. <span data-ttu-id="9c9bd-150">Dopo aver salvato il profilo, Jamf visualizza la sezione **Generale** mostrata nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-150">After you save the profile, Jamf displays the **General** section shown in the next screen shot.</span></span>

   ![Configurare la Sezione generale](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - <span data-ttu-id="9c9bd-152">Fornire un **Nome** visualizzato per il profilo e una **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-152">Provide a display **Name** for the profile and a **Description**.</span></span>
   - <span data-ttu-id="9c9bd-153">Mantenere l'impostazione predefinita per la **Categoria** ovvero **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-153">Keep the default setting for **Category**, which is **None**.</span></span>
   - <span data-ttu-id="9c9bd-154">Per **Metodo di distribuzione** le opzioni sono **Installa automaticamente** oppure **Rendi disponibile in modalità self-service**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-154">For **Distribution Method**, the options are **Install Automatically** or **Make Available in Self Service**.</span></span>
   - <span data-ttu-id="9c9bd-155">Per **Livello** le opzioni sono **Livello utente** o **Livello computer**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-155">For **Level**, the options are **User Level** or **Computer Level**.</span></span>
   - <span data-ttu-id="9c9bd-156">Fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-156">Click **Save**.</span></span>

9. <span data-ttu-id="9c9bd-157">Dopo aver salvato la Sezione generale, Jamf visualizza il profilo di configurazione del canale Microsoft Edge Beta impostato per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-157">After you save the General section, Jamf shows the "Microsoft Edge Beta Channel" configuration profile set up for our example.</span></span> <span data-ttu-id="9c9bd-158">Nella schermata successiva, tenere presente che è possibile continuare a usare il profilo facendo clic **Modifica** oppure, se si è terminato, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-158">In the next screen shot, note that you can keep working the profile by clicking **Edit** or if you're finished, click **Done**.</span></span>

   ![Nuovo profilo di configurazione con opzioni](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > <span data-ttu-id="9c9bd-160">È possibile modificare il profilo dopo che è stato salvato e in un'altra sessione di Jamf.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-160">You can edit this profile after it's been saved and in another Jamf session.</span></span> <span data-ttu-id="9c9bd-161">Ad esempio, si può decidere di modificare il metodo di distribuzione per renderla disponibile in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-161">For example, you might decide to change the Distribution Method to Make Available in Self Service.</span></span>

   <span data-ttu-id="9c9bd-162">Per eseguire una successiva modifica al canale Stable di Microsoft Edge o per eliminarlo, selezionare il nome del profilo visualizzato nella schermata Profili di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-162">To do a follow up edit on the Microsoft Edge Stable Channel, or delete it, select the profile name, shown in the following Configuration Profiles screen shot.</span></span>

   ![Elenco profili di configurazione](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

<span data-ttu-id="9c9bd-164">Dopo aver creato il nuovo profilo di configurazione, è necessario configurare l'**Ambito** per il profilo.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-164">After you create the new configuration profile you still have to configure the **Scope** for the profile.</span></span>

### <a name="to-configure-the-scope"></a><span data-ttu-id="9c9bd-165">Per configurare l'ambito</span><span class="sxs-lookup"><span data-stu-id="9c9bd-165">To configure the scope</span></span>

1. <span data-ttu-id="9c9bd-166">Per **Destinazioni** specificare le impostazioni minime seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c9bd-166">For **Targets**, provide the following minimum settings:</span></span>

   - <span data-ttu-id="9c9bd-167">COMPUTER DI DESTINAZIONE.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-167">TARGET COMPUTERS.</span></span> <span data-ttu-id="9c9bd-168">Le opzioni disponibili sono: computer specifici o tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-168">The options are Specific Computers or All Computers.</span></span>
   - <span data-ttu-id="9c9bd-169">UTENTI DI DESTINAZIONE.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-169">TARGET USERS.</span></span> <span data-ttu-id="9c9bd-170">Le opzioni disponibili sono: utenti specifici o tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-170">The options are Specific Users or All Users.</span></span>
   - <span data-ttu-id="9c9bd-171">Fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-171">Click **Save**.</span></span>
2. <span data-ttu-id="9c9bd-172">Per **Limitazioni** mantenere l'impostazione predefinita: Nessuna.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-172">For **Limitations**, keep the default setting: None.</span></span> <span data-ttu-id="9c9bd-173">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-173">Click **Cancel**.</span></span>
3. <span data-ttu-id="9c9bd-174">Per **Esclusioni** mantenere l'impostazione predefinita: Nessuna.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-174">For **Exclusions**, keep the default setting: None.</span></span> <span data-ttu-id="9c9bd-175">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="9c9bd-175">Click **Cancel**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c9bd-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c9bd-176">See also</span></span>

- [<span data-ttu-id="9c9bd-177">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="9c9bd-177">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="9c9bd-178">Configurare per macOS con Intune</span><span class="sxs-lookup"><span data-stu-id="9c9bd-178">Configure for macOS with Intune</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="9c9bd-179">Configurare per Windows</span><span class="sxs-lookup"><span data-stu-id="9c9bd-179">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="9c9bd-180">Configurare per Windows con Intune</span><span class="sxs-lookup"><span data-stu-id="9c9bd-180">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
