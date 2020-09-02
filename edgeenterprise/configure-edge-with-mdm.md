---
title: Configurare Microsoft Edge con la gestione di dispositivi mobili
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 10/25/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare Microsoft Edge con la gestione di dispositivi mobili.
ms.openlocfilehash: dda35199f653b3dfb8f20b33b068c59621222b36
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980147"
---
# <span data-ttu-id="8392f-103">Configurare Microsoft Edge con la gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="8392f-103">Configure Microsoft Edge using Mobile Device Management</span></span>

<span data-ttu-id="8392f-104">Questo articolo spiega come configurare Microsoft Edge in Windows 10 con la [gestione di dispositivi mobili (MDM)](https://docs.microsoft.com/windows/client-management/mdm/) tramite l'[inserimento ADMX](https://docs.microsoft.com/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span><span class="sxs-lookup"><span data-stu-id="8392f-104">This article explains how to configure Microsoft Edge on Windows 10 using [Mobile Device Management (MDM)](https://docs.microsoft.com/windows/client-management/mdm/) by means of [ADMX Ingestion](https://docs.microsoft.com/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span> <span data-ttu-id="8392f-105">Questo articolo descrive anche:</span><span class="sxs-lookup"><span data-stu-id="8392f-105">This article also describes:</span></span>

- <span data-ttu-id="8392f-106">Come [creare un valore URI OMA (Open Mobile Alliance Uniform Resource Identifier) per i criteri di Microsoft Edge](#create-an-oma-uri-for-microsoft-edge-policies).</span><span class="sxs-lookup"><span data-stu-id="8392f-106">How to [create Open Mobile Alliance Uniform Resource Identifier (OMA-URI) for Microsoft Edge policies](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>
- <span data-ttu-id="8392f-107">Come [configurare Microsoft Edge in Intune tramite l'inserimento ADMX e i valori URI OMA personalizzati](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span><span class="sxs-lookup"><span data-stu-id="8392f-107">How to [configure Microsoft Edge in Intune using ADMX ingestion and custom OMA-URI](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

> [!NOTE]
> <span data-ttu-id="8392f-108">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="8392f-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="8392f-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8392f-109">Prerequisites</span></span>

<span data-ttu-id="8392f-110">Windows 10, con i requisiti minimi di sistema seguenti:</span><span class="sxs-lookup"><span data-stu-id="8392f-110">Windows 10, with the following minimum system requirements:</span></span>

- <span data-ttu-id="8392f-111">Windows 10, versione 1903 con [KB4512941](https://support.microsoft.com/help/4512941/) e [KB4517211](https://support.microsoft.com/help/4517211/) installati</span><span class="sxs-lookup"><span data-stu-id="8392f-111">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/help/4512941/) and [KB4517211](https://support.microsoft.com/help/4517211/) installed</span></span>
- <span data-ttu-id="8392f-112">Windows 10, versione 1809 con [KB4512534](https://support.microsoft.com/help/4512534/) e [KB4520062](https://support.microsoft.com/help/4520062/) installati</span><span class="sxs-lookup"><span data-stu-id="8392f-112">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/help/4512534/) and [KB4520062](https://support.microsoft.com/help/4520062/) installed</span></span>
- <span data-ttu-id="8392f-113">Windows 10, versione 1803 con [KB4512509](https://support.microsoft.com/help/4512509/) e [KB4519978](https://support.microsoft.com/help/4519978) installati</span><span class="sxs-lookup"><span data-stu-id="8392f-113">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/help/4512509/) and [KB4519978](https://support.microsoft.com/help/4519978) installed</span></span>
- <span data-ttu-id="8392f-114">Windows 10, versione 1709 con [KB4516071](https://support.microsoft.com/help/4516071/) e [KB4520006](https://support.microsoft.com/help/4520006) installati</span><span class="sxs-lookup"><span data-stu-id="8392f-114">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/help/4516071/) and [KB4520006](https://support.microsoft.com/help/4520006) installed</span></span>

## <span data-ttu-id="8392f-115">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8392f-115">Overview</span></span>

<span data-ttu-id="8392f-116">Puoi configurare Microsoft Edge in Windows 10 usando MDM con il provider EMM (Enterprise Mobility Management) o il provider MDM che supporta [l'inserimento ADMX](https://docs.microsoft.com/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span><span class="sxs-lookup"><span data-stu-id="8392f-116">You can configure Microsoft Edge on Windows 10 using MDM with your preferred Enterprise Mobility Management (EMM) or MDM provider that supports [ADMX Ingestion](https://docs.microsoft.com/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span>

<span data-ttu-id="8392f-117">La configurazione di Microsoft Edge con MDM è un processo in due parti:</span><span class="sxs-lookup"><span data-stu-id="8392f-117">Configuring Microsoft Edge with MDM is a two part process:</span></span>

1. <span data-ttu-id="8392f-118">Inserimento del file ADMX di Microsoft Edge nel provider EMM o MDM.</span><span class="sxs-lookup"><span data-stu-id="8392f-118">Ingesting the Microsoft Edge ADMX file into your EMM or MDM provider.</span></span> <span data-ttu-id="8392f-119">Per istruzioni su come inserire un file ADMX, vedi le istruzioni del provider.</span><span class="sxs-lookup"><span data-stu-id="8392f-119">See your provider for instructions on how to ingest an ADMX file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8392f-120">Per Microsoft Intune, vedi [Configurare Microsoft Edge in Intune tramite l'inserimento ADMX](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span><span class="sxs-lookup"><span data-stu-id="8392f-120">For Microsoft Intune, see [Configure Microsoft Edge in Intune using ADMX ingestion](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

2. <span data-ttu-id="8392f-121">[Creazione di un valore URI OMA per i criteri di Microsoft Edge](#create-an-oma-uri-for-microsoft-edge-policies).</span><span class="sxs-lookup"><span data-stu-id="8392f-121">[Creating an OMA-URI for a Microsoft Edge policy](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>

## <span data-ttu-id="8392f-122">Creare un valore URI OMA per i criteri di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8392f-122">Create an OMA-URI for Microsoft Edge policies</span></span>

<span data-ttu-id="8392f-123">Le sezioni seguenti descrivono come creare il percorso URI OMA e come cercare e definire il valore in formato XML per i criteri di ricerca obbligatori e consigliati per il browser.</span><span class="sxs-lookup"><span data-stu-id="8392f-123">The following sections describe how to create the OMA-URI path and look up and define the value in XML format for mandatory and recommended browser polices.</span></span>

<span data-ttu-id="8392f-124">Prima di iniziare, scarica il file dei modelli di criteri di Microsoft Edge (MicrosoftEdgePolicyTemplates.cab) nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise) ed estrai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="8392f-124">Before you get started download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span>

<span data-ttu-id="8392f-125">Sono disponibili tre passaggi per definire l'URI OMA:</span><span class="sxs-lookup"><span data-stu-id="8392f-125">There are three steps for defining the OMA-URI:</span></span>

1. [<span data-ttu-id="8392f-126">Creare il percorso URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-126">Create the OMA-URI path</span></span>](#create-the-oma-uri-path)
2. [<span data-ttu-id="8392f-127">Specificare il tipo di dati URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-127">Specify the OMA-URI data type</span></span>](#specify-the-data-type)
3. [<span data-ttu-id="8392f-128">Impostare il valore URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-128">Set the OMA-URI value</span></span>](#set-the-value-for-a-browser-policy)

### <span data-ttu-id="8392f-129">Creare il percorso URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-129">Create the OMA-URI path</span></span>

<span data-ttu-id="8392f-130">Usa la formula seguente come guida per la creazione dei percorsi URI OMA.</span><span class="sxs-lookup"><span data-stu-id="8392f-130">Use the following formula as a guide for creating the OMA-URI paths.</span></span> <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| <span data-ttu-id="8392f-131">Parametro</span><span class="sxs-lookup"><span data-stu-id="8392f-131">Parameter</span></span>         | <span data-ttu-id="8392f-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8392f-132">Description</span></span>                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | <span data-ttu-id="8392f-133">Usa "Edge" o il nome definito durante l'inserimento del modello amministrativo.</span><span class="sxs-lookup"><span data-stu-id="8392f-133">Use "Edge" or what you defined when ingesting the administrative template.</span></span> <span data-ttu-id="8392f-134">Se ad esempio hai usato "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx", devi usare "MicrosoftEdge".</span><span class="sxs-lookup"><span data-stu-id="8392f-134">For example, if you used "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx", then use "MicrosoftEdge".</span></span><br/><br/> <span data-ttu-id="8392f-135">Il nome `<ADMXIngestionName>` deve corrispondere a quello usato quando hai inserito il file ADMX.</span><span class="sxs-lookup"><span data-stu-id="8392f-135">The `<ADMXIngestionName>` must match what was used when you ingested the ADMX file.</span></span> |
| \<ADMXNamespace>  | <span data-ttu-id="8392f-136">"microsoft_edge" o "microsoft_edge_recommended", a seconda che il criterio impostato sia obbligatorio o consigliato.</span><span class="sxs-lookup"><span data-stu-id="8392f-136">Either "microsoft_edge" or "microsoft_edge_recommended" depending on whether you're setting a mandatory or recommended policy.</span></span> |
| \<ADMXCategory>   | <span data-ttu-id="8392f-137">L'elemento "parentCategory" del criterio è definito nel file ADMX.</span><span class="sxs-lookup"><span data-stu-id="8392f-137">The "parentCategory" of the policy is defined in the ADMX file.</span></span> <span data-ttu-id="8392f-138">Ometti `<ADMXCategory>` se il criterio non è in gruppo (nessune elemento "parentCategory" definito).</span><span class="sxs-lookup"><span data-stu-id="8392f-138">Omit the `<ADMXCategory>` if the policy isn't grouped (No "parentCategory" defined).</span></span> |
| \<PolicyName>     | <span data-ttu-id="8392f-139">Il nome del criterio è disponibile nell'articolo [Informazioni di riferimento sui criteri del browser](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies).</span><span class="sxs-lookup"><span data-stu-id="8392f-139">The policy name can be found in the [Browser policy reference](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) article.</span></span> |

#### <span data-ttu-id="8392f-140">Esempio di percorso URI</span><span class="sxs-lookup"><span data-stu-id="8392f-140">URI path example:</span></span>

<span data-ttu-id="8392f-141">Per questo esempio, assumi che il nodo `<ADMXIngestName>` sia stato denominato "Edge" e che tu stia impostando un criterio obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8392f-141">For this example, assume the `<ADMXIngestName>` node was named “Edge" and you're setting a mandatory policy.</span></span> <span data-ttu-id="8392f-142">Il percorso URI sarebbe:</span><span class="sxs-lookup"><span data-stu-id="8392f-142">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

<span data-ttu-id="8392f-143">Se il criterio non appartiene a un gruppo (ad esempio DiskCacheSize), rimuovi "`~<ADMXCategory>`".</span><span class="sxs-lookup"><span data-stu-id="8392f-143">If the policy isn't in a group (for example, DiskCacheSize) remove "`~<ADMXCategory>`".</span></span> <span data-ttu-id="8392f-144">Sostituisci `<PolicyName>` con il nome del criterio, DiskCacheSize.</span><span class="sxs-lookup"><span data-stu-id="8392f-144">Replace `<PolicyName>` with the name of the policy, DiskCacheSize.</span></span> <span data-ttu-id="8392f-145">Il percorso URI sarebbe:</span><span class="sxs-lookup"><span data-stu-id="8392f-145">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

<span data-ttu-id="8392f-146">Se il criterio appartiene a un gruppo, segui questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8392f-146">If the policy is in a group, follow these steps:</span></span>

1. <span data-ttu-id="8392f-147">Apri **msedge.admx** con qualsiasi editor XML.</span><span class="sxs-lookup"><span data-stu-id="8392f-147">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="8392f-148">Cerca il nome del criterio che vuoi applicare.</span><span class="sxs-lookup"><span data-stu-id="8392f-148">Search for the policy name you want to set.</span></span> <span data-ttu-id="8392f-149">Ad esempio, "ExtensionInstallForceList".</span><span class="sxs-lookup"><span data-stu-id="8392f-149">For example, "ExtensionInstallForceList".</span></span>
3. <span data-ttu-id="8392f-150">Usa il valore dell'attributo *ref* dell'elemento *parentCategory*.</span><span class="sxs-lookup"><span data-stu-id="8392f-150">Use the value of the *ref* attribute from the *parentCategory* element.</span></span> <span data-ttu-id="8392f-151">Ad esempio, "estensioni" da \<parentCategory ref=" Extensions"/>.</span><span class="sxs-lookup"><span data-stu-id="8392f-151">For example, "Extensions" from \<parentCategory ref=" Extensions"/>.</span></span>
4. <span data-ttu-id="8392f-152">Sostituisci `<ADMXCategory>` con il valore dell'attributo *ref* per creare il percorso URI.</span><span class="sxs-lookup"><span data-stu-id="8392f-152">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path.</span></span> <span data-ttu-id="8392f-153">Il percorso URI sarebbe:</span><span class="sxs-lookup"><span data-stu-id="8392f-153">The URI path would be:</span></span><br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <span data-ttu-id="8392f-154">Specificare il tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8392f-154">Specify the data type</span></span>

<span data-ttu-id="8392f-155">Il tipo di dati URI OMA è sempre “String”.</span><span class="sxs-lookup"><span data-stu-id="8392f-155">The OMA-URI data type is always “String”.</span></span>

### <span data-ttu-id="8392f-156">Impostare il valore per un criterio del browser</span><span class="sxs-lookup"><span data-stu-id="8392f-156">Set the value for a browser policy</span></span>

<span data-ttu-id="8392f-157">In questa sezione viene descritto come impostare il valore, in formato XML, per ogni tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="8392f-157">This section describes how to set the value, in XML format, for each data type.</span></span> <span data-ttu-id="8392f-158">Vai a [Informazioni di riferimento sui criteri del browser](https://docs.microsoft.com/deployedge/microsoft-edge-policies) per cercare il tipo di dati del criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-158">Go to [Browser policy reference](https://docs.microsoft.com/deployedge/microsoft-edge-policies) to look up the data type of the policy.</span></span>

> [!NOTE]
> <span data-ttu-id="8392f-159">Per i tipi di dati non Boolean, il valore inizia sempre con `<enabled/>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-159">For non-Boolean data types, the value always starts with `<enabled/>`.</span></span>

#### <span data-ttu-id="8392f-160">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="8392f-160">Boolean data type</span></span>

<span data-ttu-id="8392f-161">Per i criteri con tipi Boolean usa `<enabled/>` o `<disabled/>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-161">For policies that are Boolean types use `<enabled/>` or `<disabled/>`.</span></span>

#### <span data-ttu-id="8392f-162">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="8392f-162">Integer data type</span></span>

<span data-ttu-id="8392f-163">Il valore inizia sempre con l'elemento `<enabled/>` seguito da `<data id="[valueName]" value="[decimal value]"/>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-163">The value always needs to start with the `<enabled/>` element followed by `<data id="[valueName]" value="[decimal value]"/>`.</span></span>

<span data-ttu-id="8392f-164">Per trovare il nome del valore e il valore decimale per una pagina Nuova scheda, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8392f-164">To find the value name and decimal value for a new tab page, use the following steps:</span></span>

1. <span data-ttu-id="8392f-165">Apri **msedge.admx** con qualsiasi editor XML.</span><span class="sxs-lookup"><span data-stu-id="8392f-165">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="8392f-166">Cerca l'elemento `<policy>` in cui l'attributo del nome corrisponde al nome del criterio da impostare.</span><span class="sxs-lookup"><span data-stu-id="8392f-166">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="8392f-167">Per "RestoreOnStartup", cerca `name="RestoreOnStartup"`.</span><span class="sxs-lookup"><span data-stu-id="8392f-167">For "RestoreOnStartup", search for `name="RestoreOnStartup"`.</span></span>
3. <span data-ttu-id="8392f-168">Nel nodo `<elements>`, trova il valore da impostare.</span><span class="sxs-lookup"><span data-stu-id="8392f-168">In the `<elements>` node, find the value you want to set.</span></span>
4. <span data-ttu-id="8392f-169">Usa il valore nell'attributo "valueName" nel nodo `<elements>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-169">Use the value in the "valueName" attribute in the `<elements>` node.</span></span> <span data-ttu-id="8392f-170">Per "RestoreOnStartup" il valore "valueName" è "RestoreOnStartup".</span><span class="sxs-lookup"><span data-stu-id="8392f-170">For "RestoreOnStartup" the "valueName" is "RestoreOnStartup".</span></span>
5. <span data-ttu-id="8392f-171">Usa il valore nell'attributo "value" nel nodo `<decimal>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-171">Use the value in the "value" attribute in the `<decimal>` node.</span></span> <span data-ttu-id="8392f-172">Per "RestoreOnStartup", per aprire la pagina Nuova scheda il valore è "5".</span><span class="sxs-lookup"><span data-stu-id="8392f-172">For "RestoreOnStartup" to open the new tab page the value is "5".</span></span>

<span data-ttu-id="8392f-173">Per aprire la pagina Nuova scheda all'avvio usa:</span><span class="sxs-lookup"><span data-stu-id="8392f-173">To open the new tab page on startup use:</span></span><br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <span data-ttu-id="8392f-174">Elenco di tipi di dati stringhe</span><span class="sxs-lookup"><span data-stu-id="8392f-174">List of strings data type</span></span>

<span data-ttu-id="8392f-175">Il valore inizia sempre con l'elemento `<enabled/>` seguito da `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-175">The value always needs to start with the `<enabled/>` element followed by `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`.</span></span>

> [!NOTE]
> <span data-ttu-id="8392f-176">Il nome dell'attributo "id=" non è il nome del criterio, anche se nella maggior parte dei casi corrisponde al nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-176">The "id=" attribute name isn't the policy name, even though in most cases it matches the policy name.</span></span> <span data-ttu-id="8392f-177">Si tratta del valore dell'attributo ID del nodo \<list> presente nel file ADMX.</span><span class="sxs-lookup"><span data-stu-id="8392f-177">It's the \<list> node id attribute value, which is found in the ADMX file.</span></span>

<span data-ttu-id="8392f-178">Per trovare l'elemento listID e definire il valore per bloccare un URL, esegui queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="8392f-178">To find the listID and define the value to block a URL, follow these steps:</span></span>

1. <span data-ttu-id="8392f-179">Apri **msedge.admx** con qualsiasi editor XML.</span><span class="sxs-lookup"><span data-stu-id="8392f-179">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="8392f-180">Cerca l'elemento `<policy>` in cui l'attributo del nome corrisponde al nome del criterio da impostare.</span><span class="sxs-lookup"><span data-stu-id="8392f-180">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="8392f-181">Per "URLBlocklist", cerca `name="URLBlocklist"`.</span><span class="sxs-lookup"><span data-stu-id="8392f-181">For "URLBlocklist", search for `name="URLBlocklist"`.</span></span>
3. <span data-ttu-id="8392f-182">Usa il valore dell'attributo "id" dell'elemento `<list> node for [listID]`.</span><span class="sxs-lookup"><span data-stu-id="8392f-182">Use the value in the "id" attribute of the `<list> node for [listID]`.</span></span>
4. <span data-ttu-id="8392f-183">L'elemento "value" è un elenco di URL separati da un punto e virgola (;)</span><span class="sxs-lookup"><span data-stu-id="8392f-183">The "value" is a list of URLs separated by a semicolon (;)</span></span>

<span data-ttu-id="8392f-184">Ad esempio, per bloccare l'accesso a `contoso.com` e `https://ssl.server.com`:</span><span class="sxs-lookup"><span data-stu-id="8392f-184">For example, to block access to `contoso.com` and `https://ssl.server.com`:</span></span><br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <span data-ttu-id="8392f-185">Tipo di dati Dictionary o String</span><span class="sxs-lookup"><span data-stu-id="8392f-185">Dictionary or String data type</span></span>

<span data-ttu-id="8392f-186">Il valore deve sempre iniziare con l'elemento `<enabled/>` seguito da `<data id="[textID]" value="[string]"/>` .</span><span class="sxs-lookup"><span data-stu-id="8392f-186">The value always needs to start with the `<enabled/>` followed by `<data id="[textID]" value="[string]"/>` .</span></span>

<span data-ttu-id="8392f-187">Per trovare l'elemento textID e definire il valore per impostare le impostazioni locali, esegui queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="8392f-187">To find the textID and define the value set the locale, follow these steps:</span></span>

1. <span data-ttu-id="8392f-188">Apri **msedge.admx** con qualsiasi editor XML.</span><span class="sxs-lookup"><span data-stu-id="8392f-188">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="8392f-189">Cerca l'elemento `<policy>` in cui l'attributo del nome corrisponde al nome del criterio da impostare.</span><span class="sxs-lookup"><span data-stu-id="8392f-189">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="8392f-190">Per "ApplicationLocaleValue" cerca `name="ApplicationLocaleValue"`.</span><span class="sxs-lookup"><span data-stu-id="8392f-190">For "ApplicationLocaleValue", search for `name="ApplicationLocaleValue"`.</span></span>
3. <span data-ttu-id="8392f-191">Usa il valore dell'attributo "id" del nodo `<text>` per `[textID]`.</span><span class="sxs-lookup"><span data-stu-id="8392f-191">Use the value in the "id" attribute of the `<text>` node for `[textID]`.</span></span>
4. <span data-ttu-id="8392f-192">Imposta l'elemento "value" sul codice relativo alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="8392f-192">Set the "value" to the culture code.</span></span>

<span data-ttu-id="8392f-193">Per impostare le impostazioni locali su "es-US" con il criterio "ApplicationLocaleValue":</span><span class="sxs-lookup"><span data-stu-id="8392f-193">To set the locale to "es-US" with the "ApplicationLocaleValue" policy:</span></span><br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

### <span data-ttu-id="8392f-194">Creare l'URI OMA per un criterio consigliato</span><span class="sxs-lookup"><span data-stu-id="8392f-194">Create the OMA-URI for a recommended policies</span></span>

<span data-ttu-id="8392f-195">La definizione del percorso URI per i criteri consigliati dipende dal criterio che desideri configurare.</span><span class="sxs-lookup"><span data-stu-id="8392f-195">Defining the URI path for recommended policies depends on the policy you want to configure.</span></span>

#### <span data-ttu-id="8392f-196">Per definire il percorso URI per un criterio consigliato</span><span class="sxs-lookup"><span data-stu-id="8392f-196">To define the URI path for a recommended policy</span></span>

<span data-ttu-id="8392f-197">Usa la formula del percorso URI (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) e i passaggi seguenti per definire il percorso URI:</span><span class="sxs-lookup"><span data-stu-id="8392f-197">Use the URI path formula (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) and the following steps to define the URI path:</span></span>

1. <span data-ttu-id="8392f-198">Apri **msedge.admx** con qualsiasi editor XML.</span><span class="sxs-lookup"><span data-stu-id="8392f-198">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="8392f-199">Se il criterio da configurare non è incluso in un gruppo, vai al passaggio 4 e rimuovi `~<ADMXCategory>` dal percorso.</span><span class="sxs-lookup"><span data-stu-id="8392f-199">If the policy you want to configure isn't in a group, skip to step 4 and remove `~<ADMXCategory>` from the path.</span></span>
3. <span data-ttu-id="8392f-200">Se il criterio da configurare si trova in un gruppo:</span><span class="sxs-lookup"><span data-stu-id="8392f-200">If the policy you want to configure is in a group:</span></span>

   - <span data-ttu-id="8392f-201">Per cercare `<ADMXCategory>`, cerca il criterio da impostare.</span><span class="sxs-lookup"><span data-stu-id="8392f-201">To look up the `<ADMXCategory>`, search for the policy you want to set.</span></span> <span data-ttu-id="8392f-202">Durante la ricerca, aggiungi "_recommended" al nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-202">When searching append "_recommended" to the policy name.</span></span> <span data-ttu-id="8392f-203">Ad esempio, una ricerca per "RegisteredProtocolHandlers_recommended" restituisce il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="8392f-203">For example, a search for "RegisteredProtocolHandlers_recommended” has the following result:</span></span>

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - <span data-ttu-id="8392f-204">Copia il valore dell'attributo *ref* dall'elemento `<parentCategory>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-204">Copy the value of the *ref* attribute from the `<parentCategory>` element.</span></span> <span data-ttu-id="8392f-205">Per "ContentSettings", copia "ContentSettings_recommended" da `<parentCategory ref=" ContentSettings_recommended"/>`.</span><span class="sxs-lookup"><span data-stu-id="8392f-205">For "ContentSettings", copy "ContentSettings_recommended" from `<parentCategory ref=" ContentSettings_recommended"/>`.</span></span>
   - <span data-ttu-id="8392f-206">Sostituisci `<ADMXCategory>` con il valore dell'attributo *ref* per creare il percorso URI nella formula relativa.</span><span class="sxs-lookup"><span data-stu-id="8392f-206">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path in the URI path formula.</span></span>

4. <span data-ttu-id="8392f-207">`<PolicyName>` è il nome del criterio con il suffisso "_recommended".</span><span class="sxs-lookup"><span data-stu-id="8392f-207">The `<PolicyName>` is the name of the policy with "_recommended" appended to it.</span></span>

#### <span data-ttu-id="8392f-208">Esempi di percorso URI OMA per i criteri consigliati</span><span class="sxs-lookup"><span data-stu-id="8392f-208">OMA-URI path examples for recommended policies</span></span>

<span data-ttu-id="8392f-209">Nella tabella seguente sono riportati alcuni esempi di percorsi URI OMA per i criteri consigliati.</span><span class="sxs-lookup"><span data-stu-id="8392f-209">The following table shows examples of OMA-URI paths for recommended policies.</span></span>

|              <span data-ttu-id="8392f-210">Criterio</span><span class="sxs-lookup"><span data-stu-id="8392f-210">Policy</span></span>               |             <span data-ttu-id="8392f-211">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-211">OMA-URI</span></span>                      |
|-----------------------------------|------------------------------------------|
| [<span data-ttu-id="8392f-212">RegisteredProtocolHandlers</span><span class="sxs-lookup"><span data-stu-id="8392f-212">RegisteredProtocolHandlers</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [<span data-ttu-id="8392f-213">PasswordManagerEnabled</span><span class="sxs-lookup"><span data-stu-id="8392f-213">PasswordManagerEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [<span data-ttu-id="8392f-214">PrintHeaderFooter</span><span class="sxs-lookup"><span data-stu-id="8392f-214">PrintHeaderFooter</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [<span data-ttu-id="8392f-215">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="8392f-215">SmartScreenEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [<span data-ttu-id="8392f-216">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="8392f-216">HomePageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [<span data-ttu-id="8392f-217">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="8392f-217">ShowHomeButton</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [<span data-ttu-id="8392f-218">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="8392f-218">FavoritesBarEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <span data-ttu-id="8392f-219">Esempi URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-219">OMA-URI examples</span></span>

<span data-ttu-id="8392f-220">Esempi di URI OMA con il percorso URI, il tipo e un valore di esempio.</span><span class="sxs-lookup"><span data-stu-id="8392f-220">OMA-URI examples with their URI path, type, and an example value.</span></span>

#### <span data-ttu-id="8392f-221">Esempi di tipi di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="8392f-221">Boolean data type examples</span></span>

*<span data-ttu-id="8392f-222">[ShowHomeButton](https://docs.microsoft.com/deployedge/microsoft-edge-policies#ShowHomeButton):</span><span class="sxs-lookup"><span data-stu-id="8392f-222">[ShowHomeButton](https://docs.microsoft.com/deployedge/microsoft-edge-policies#ShowHomeButton):</span></span>*

| <span data-ttu-id="8392f-223">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-223">Field</span></span>   | <span data-ttu-id="8392f-224">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-224">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-225">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-225">Name</span></span>    | <span data-ttu-id="8392f-226">Microsoft Edge: ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="8392f-226">Microsoft Edge: ShowHomeButton</span></span>                                                       |
| <span data-ttu-id="8392f-227">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-227">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| <span data-ttu-id="8392f-228">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-228">type</span></span>    | <span data-ttu-id="8392f-229">String</span><span class="sxs-lookup"><span data-stu-id="8392f-229">String</span></span>                                                                               |
| <span data-ttu-id="8392f-230">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-230">Value</span></span>   | `<enabled/>`                                                                          |

*<span data-ttu-id="8392f-231">[DefaultSearchProviderEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#DefaultSearchProviderEnabled):</span><span class="sxs-lookup"><span data-stu-id="8392f-231">[DefaultSearchProviderEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#DefaultSearchProviderEnabled):</span></span>*

| <span data-ttu-id="8392f-232">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-232">Field</span></span>   | <span data-ttu-id="8392f-233">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-233">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-234">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-234">Name</span></span>    | <span data-ttu-id="8392f-235">Microsoft Edge: DefaultSearchProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="8392f-235">Microsoft Edge: DefaultSearchProviderEnabled</span></span>                                         |
| <span data-ttu-id="8392f-236">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-236">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| <span data-ttu-id="8392f-237">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-237">type</span></span>    | <span data-ttu-id="8392f-238">String</span><span class="sxs-lookup"><span data-stu-id="8392f-238">String</span></span>                                                                               |
| <span data-ttu-id="8392f-239">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-239">Value</span></span>   | `<disable/>`                                                                          |

### <span data-ttu-id="8392f-240">Esempi di tipi di dati Integer</span><span class="sxs-lookup"><span data-stu-id="8392f-240">Integer data type examples</span></span>

*<span data-ttu-id="8392f-241">[AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#AutoImportAtFirstRun):</span><span class="sxs-lookup"><span data-stu-id="8392f-241">[AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#AutoImportAtFirstRun):</span></span>*

| <span data-ttu-id="8392f-242">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-242">Field</span></span>   | <span data-ttu-id="8392f-243">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-243">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-244">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-244">Name</span></span>    | <span data-ttu-id="8392f-245">Microsoft Edge: AutoImportAtFirstRun</span><span class="sxs-lookup"><span data-stu-id="8392f-245">Microsoft Edge: AutoImportAtFirstRun</span></span>                                                 |
| <span data-ttu-id="8392f-246">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-246">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| <span data-ttu-id="8392f-247">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-247">type</span></span>    | <span data-ttu-id="8392f-248">String</span><span class="sxs-lookup"><span data-stu-id="8392f-248">String</span></span>                                                                               |
| <span data-ttu-id="8392f-249">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-249">Value</span></span>   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*<span data-ttu-id="8392f-250">[DefaultImagesSetting](https://docs.microsoft.com/deployedge/microsoft-edge-policies#DefaultImagesSetting):</span><span class="sxs-lookup"><span data-stu-id="8392f-250">[DefaultImagesSetting](https://docs.microsoft.com/deployedge/microsoft-edge-policies#DefaultImagesSetting):</span></span>*

| <span data-ttu-id="8392f-251">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-251">Field</span></span>   | <span data-ttu-id="8392f-252">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-252">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-253">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-253">Name</span></span>    | <span data-ttu-id="8392f-254">Microsoft Edge: DefaultImagesSetting</span><span class="sxs-lookup"><span data-stu-id="8392f-254">Microsoft Edge: DefaultImagesSetting</span></span>                                                 |
| <span data-ttu-id="8392f-255">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-255">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| <span data-ttu-id="8392f-256">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-256">type</span></span>    | <span data-ttu-id="8392f-257">String</span><span class="sxs-lookup"><span data-stu-id="8392f-257">String</span></span>                                                                               |
| <span data-ttu-id="8392f-258">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-258">Value</span></span>   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*<span data-ttu-id="8392f-259">[DiskCacheSize](https://docs.microsoft.com/deployedge/microsoft-edge-policies#DiskCacheSize):</span><span class="sxs-lookup"><span data-stu-id="8392f-259">[DiskCacheSize](https://docs.microsoft.com/deployedge/microsoft-edge-policies#DiskCacheSize):</span></span>*

| <span data-ttu-id="8392f-260">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-260">Field</span></span>   | <span data-ttu-id="8392f-261">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-261">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-262">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-262">Name</span></span>    | <span data-ttu-id="8392f-263">Microsoft Edge: DiskCacheSize</span><span class="sxs-lookup"><span data-stu-id="8392f-263">Microsoft Edge: DiskCacheSize</span></span>                                                        |
| <span data-ttu-id="8392f-264">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-264">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| <span data-ttu-id="8392f-265">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-265">type</span></span>    | <span data-ttu-id="8392f-266">String</span><span class="sxs-lookup"><span data-stu-id="8392f-266">String</span></span>                                                                               |
| <span data-ttu-id="8392f-267">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-267">Value</span></span>   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <span data-ttu-id="8392f-268">Elenco di esempi di tipi di dati String</span><span class="sxs-lookup"><span data-stu-id="8392f-268">List of strings data type examples</span></span>
<!--
*[NotificationsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#NotificationsAllowedForUrls):*

| Field   | Value                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Name    | Microsoft Edge: NotificationsAllowedForUrls                                          |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/NotificationsAllowedForUrls`    |
| Type    | String                                                                               |
| Value   | `<enabled/><data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com"/>`<br>For multiple list items: `<data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com;[*.]contoso.edu"/>`                               |
-->
*<span data-ttu-id="8392f-269">[RestoreOnStartupURLS](https://docs.microsoft.com/deployedge/microsoft-edge-policies#RestoreOnStartupURLS):</span><span class="sxs-lookup"><span data-stu-id="8392f-269">[RestoreOnStartupURLS](https://docs.microsoft.com/deployedge/microsoft-edge-policies#RestoreOnStartupURLS):</span></span>*

| <span data-ttu-id="8392f-270">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-270">Field</span></span>   | <span data-ttu-id="8392f-271">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-271">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-272">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-272">Name</span></span>    | <span data-ttu-id="8392f-273">Microsoft Edge: RestoreOnStartupURLS</span><span class="sxs-lookup"><span data-stu-id="8392f-273">Microsoft Edge: RestoreOnStartupURLS</span></span>                                                 |
| <span data-ttu-id="8392f-274">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-274">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| <span data-ttu-id="8392f-275">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-275">Type</span></span>    | <span data-ttu-id="8392f-276">String</span><span class="sxs-lookup"><span data-stu-id="8392f-276">String</span></span>                                                                               |
| <span data-ttu-id="8392f-277">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-277">Value</span></span>   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br><span data-ttu-id="8392f-278">Per elementi di più elenchi:</span><span class="sxs-lookup"><span data-stu-id="8392f-278">For multiple list items:</span></span> `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*<span data-ttu-id="8392f-279">[ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#ExtensionInstallForcelist):</span><span class="sxs-lookup"><span data-stu-id="8392f-279">[ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#ExtensionInstallForcelist):</span></span>*

| <span data-ttu-id="8392f-280">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-280">Field</span></span>   | <span data-ttu-id="8392f-281">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-281">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-282">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-282">Name</span></span>    | <span data-ttu-id="8392f-283">Microsoft Edge: ExtensionInstallForcelist</span><span class="sxs-lookup"><span data-stu-id="8392f-283">Microsoft Edge: ExtensionInstallForcelist</span></span>                                            |
| <span data-ttu-id="8392f-284">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-284">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| <span data-ttu-id="8392f-285">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-285">Type</span></span>    | <span data-ttu-id="8392f-286">String</span><span class="sxs-lookup"><span data-stu-id="8392f-286">String</span></span>                                                                               |
| <span data-ttu-id="8392f-287">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-287">Value</span></span>   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <span data-ttu-id="8392f-288">Esempio di tipo di dati Dictionary e String</span><span class="sxs-lookup"><span data-stu-id="8392f-288">Dictionary and String data type example</span></span>

*<span data-ttu-id="8392f-289">[ProxyMode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#ProxyMode):</span><span class="sxs-lookup"><span data-stu-id="8392f-289">[ProxyMode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#ProxyMode):</span></span>*

| <span data-ttu-id="8392f-290">Campo</span><span class="sxs-lookup"><span data-stu-id="8392f-290">Field</span></span>   | <span data-ttu-id="8392f-291">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-291">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="8392f-292">Nome</span><span class="sxs-lookup"><span data-stu-id="8392f-292">Name</span></span>    | <span data-ttu-id="8392f-293">Microsoft Edge: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="8392f-293">Microsoft Edge: ProxyMode</span></span>                                                            |
| <span data-ttu-id="8392f-294">URI OMA</span><span class="sxs-lookup"><span data-stu-id="8392f-294">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| <span data-ttu-id="8392f-295">Tipo</span><span class="sxs-lookup"><span data-stu-id="8392f-295">Type</span></span>    | <span data-ttu-id="8392f-296">String</span><span class="sxs-lookup"><span data-stu-id="8392f-296">String</span></span>                                                                               |
| <span data-ttu-id="8392f-297">Valore</span><span class="sxs-lookup"><span data-stu-id="8392f-297">Value</span></span>   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

## <span data-ttu-id="8392f-298">Configurare Microsoft Edge in Intune tramite l'inserimento ADMX</span><span class="sxs-lookup"><span data-stu-id="8392f-298">Configure Microsoft Edge in Intune using ADMX ingestion</span></span>

<span data-ttu-id="8392f-299">Il modo consigliato per configurare Microsoft Edge con Microsoft Intune è quello di usare il profilo dei modelli amministrativi come descritto in [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="8392f-299">The recommended way to configure Microsoft Edge with Microsoft Intune is to use the Administrative Templates profile as described in [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="8392f-300">Se desideri valutare un criterio attualmente non disponibile nei modelli amministrativi di Microsoft Edge in Intune, puoi configurare Microsoft Edge tramite le [impostazioni personalizzate per i dispositivi Windows 10 in Intune](https://docs.microsoft.com/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="8392f-300">If you want to evaluate a policy that is currently not available in the Microsoft Edge Administrative Templates in Intune you can configure Microsoft Edge using  [custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/intune/configuration/custom-settings-windows-10).</span></span>

<span data-ttu-id="8392f-301">Questa sezione descrive come:</span><span class="sxs-lookup"><span data-stu-id="8392f-301">This section describes how to:</span></span>

1. [<span data-ttu-id="8392f-302">Inserire il file ADMX di Microsoft Edge in Intune</span><span class="sxs-lookup"><span data-stu-id="8392f-302">Ingest the Microsoft Edge ADMX file into Intune</span></span>](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [<span data-ttu-id="8392f-303">Impostare un criterio tramite l'URI OMA personalizzato in Intune</span><span class="sxs-lookup"><span data-stu-id="8392f-303">Set a policy using custom OMA-URI in Intune</span></span>](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> <span data-ttu-id="8392f-304">Come procedura consigliata, non usare un profilo URI OMA personalizzato né un profilo di modelli di amministrazione per configurare la stessa impostazione Microsoft Edge in Intune.</span><span class="sxs-lookup"><span data-stu-id="8392f-304">As a best practice, don’t use a custom OMA-URI profile and an Administration templates profile to configure the same Microsoft Edge setting in Intune.</span></span> <span data-ttu-id="8392f-305">Se distribuisci gli stessi criteri usando un URI OMA personalizzato e un profilo del modello amministrativo, ma con valori diversi, gli utenti otterranno risultati imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="8392f-305">If you deploy the same policy using both a custom OMA-URI  and an Administrative template profile, but with different values, users will get unpredictable results.</span></span> <span data-ttu-id="8392f-306">Ti consigliamo di rimuovere il profilo URI OMA prima di usare un profilo di modelli di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="8392f-306">We strongly recommend removing your OMA-URI profile before using an Administration templates profile.</span></span>

### <span data-ttu-id="8392f-307">Inserire il file ADMX di Microsoft Edge in Intune</span><span class="sxs-lookup"><span data-stu-id="8392f-307">Ingest the Microsoft Edge ADMX file into Intune</span></span>

<span data-ttu-id="8392f-308">In questa sezione viene descritto come inserire il modello amministrativo di Microsoft Edge (file **msedge.admx**) in Intune.</span><span class="sxs-lookup"><span data-stu-id="8392f-308">This section describes how to ingest the Microsoft Edge administrative template (**msedge.admx** file) into Intune.</span></span>

> [!WARNING]
> <span data-ttu-id="8392f-309">Non modificare il file ADMX prima di inserirlo.</span><span class="sxs-lookup"><span data-stu-id="8392f-309">Don't modify the ADMX file before ingesting the file.</span></span>

<span data-ttu-id="8392f-310">Per inserire il file ADMX, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="8392f-310">To ingest the ADMX file, follow these steps:</span></span>

1. <span data-ttu-id="8392f-311">Scarica il file dei modelli dei criteri di Microsoft Edge (MicrosoftEdgePolicyTemplates.cab) nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise) ed estrai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="8392f-311">Download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span> <span data-ttu-id="8392f-312">Il file da inserire è **msedge. admx**.</span><span class="sxs-lookup"><span data-stu-id="8392f-312">The file that you want to ingest is **msedge.admx**.</span></span>
2. <span data-ttu-id="8392f-313">Accedi al [portale di Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8392f-313">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
3. <span data-ttu-id="8392f-314">Seleziona **Intune** in _Tutti i servizi_ oppure cerca Intune nella casella di ricerca del portale.</span><span class="sxs-lookup"><span data-stu-id="8392f-314">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
4. <span data-ttu-id="8392f-315">Nel pannello _Microsoft Intune - Panoramica_ seleziona **Configurazione del dispositivo** | **Profili**.</span><span class="sxs-lookup"><span data-stu-id="8392f-315">From _Microsoft Intune - Overview_, select **Device configuration** | **Profiles**.</span></span>
5. <span data-ttu-id="8392f-316">Sulla barra dei comandi superiore seleziona **+ Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="8392f-316">On the top command bar, select **+ Create profile**.</span></span>

   ![Creare un profilo del dispositivo](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. <span data-ttu-id="8392f-318">Specifica le informazioni sul profilo seguenti:</span><span class="sxs-lookup"><span data-stu-id="8392f-318">Provide the following profile information:</span></span>

   - <span data-ttu-id="8392f-319">**Nome**: immetti un nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="8392f-319">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="8392f-320">Per questo esempio immetti "Configurazione inserita ADMX Microsoft Edge".</span><span class="sxs-lookup"><span data-stu-id="8392f-320">For this example, "Microsoft Edge ADMX ingested configuration".</span></span>
   - <span data-ttu-id="8392f-321">**Descrizione**: immetti una descrizione facoltativa per il profilo.</span><span class="sxs-lookup"><span data-stu-id="8392f-321">**Description**: Enter an optional description for the profile.</span></span>
   - <span data-ttu-id="8392f-322">**Piattaforma**: seleziona "Windows 10 e versioni successive"</span><span class="sxs-lookup"><span data-stu-id="8392f-322">**Platform**: Select "Windows 10 and later"</span></span>
   - <span data-ttu-id="8392f-323">**Tipo di profilo**: seleziona "Personalizzato"</span><span class="sxs-lookup"><span data-stu-id="8392f-323">**Profile type**: Select "Custom"</span></span>

7. <span data-ttu-id="8392f-324">In **Impostazioni OMA-URI personalizzate** fai clic su **Aggiungi** per aggiungere un inserimento ADMX.</span><span class="sxs-lookup"><span data-stu-id="8392f-324">On **Custom OMA-URI Settings**, click **Add** to add an ADMX ingestion.</span></span>

   ![Aggiungere un inserimento per URI OMA](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. <span data-ttu-id="8392f-326">In **Aggiungi riga** specifica le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8392f-326">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="8392f-327">**Nome**: immetti un nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="8392f-327">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="8392f-328">Per questo esempio usai "Inserimento ADMX Microsoft Edge".</span><span class="sxs-lookup"><span data-stu-id="8392f-328">For this example, use "Microsoft Edge ADMX ingestion".</span></span>
   - <span data-ttu-id="8392f-329">**Descrizione**: immetti una descrizione facoltativa per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="8392f-329">**Description**: Enter an optional description for the setting.</span></span>
   - <span data-ttu-id="8392f-330">**OMA-URI**: immetti "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"</span><span class="sxs-lookup"><span data-stu-id="8392f-330">**OMA-URI**: Enter "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"</span></span>
   - <span data-ttu-id="8392f-331">**Tipo di dati**: seleziona "String"</span><span class="sxs-lookup"><span data-stu-id="8392f-331">**Data type**: Select "String"</span></span>
   - <span data-ttu-id="8392f-332">**Valore**: questa area di input viene visualizzata dopo che hai selezionato **Tipo di dati**.</span><span class="sxs-lookup"><span data-stu-id="8392f-332">**Value**: This input area appears after you select the **Data type**.</span></span> <span data-ttu-id="8392f-333">Aprire il file msedge.admx dal file dei modelli di criteri di Microsoft Edge estratto nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="8392f-333">Open the msedge.admx file from the Microsoft Edge policy templates file you extracted in step 1.</span></span> <span data-ttu-id="8392f-334">Copia **TUTTO il testo** dal file msedge.admx e incollalo nell'area di testo **Valore** mostrata nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="8392f-334">Copy **ALL the text** from the msedge.admx file and paste it in the **Value** text area shown in the following screenshot.</span></span>

        ![Aggiungere un inserimento ADMX](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - <span data-ttu-id="8392f-336">Fai clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8392f-336">Click **OK**.</span></span>

9. <span data-ttu-id="8392f-337">In **Impostazioni OMA-URI personalizzate** fai clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8392f-337">On **Custom OMA-URI Settings**, click **OK**.</span></span>
10. <span data-ttu-id="8392f-338">In **Crea profilo** fai clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="8392f-338">On **Create profile**, click **Create**.</span></span> <span data-ttu-id="8392f-339">Nella schermata successiva vengono visualizzate le informazioni sul profilo creato.</span><span class="sxs-lookup"><span data-stu-id="8392f-339">The next screenshot shows information about the newly created profile.</span></span>

    ![<span data-ttu-id="8392f-340">Informazioni sul nuovo profilo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="8392f-340">New device profile information</span></span> ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <span data-ttu-id="8392f-341">Impostare un criterio tramite l'URI OMA personalizzato in Intune</span><span class="sxs-lookup"><span data-stu-id="8392f-341">Set a policy using custom OMA-URI in Intune</span></span>

> [!NOTE]
> <span data-ttu-id="8392f-342">Prima di usare i passaggi illustrati in questa sezione, devi completare i passaggi descritti in [Inserire il file ADMX di Microsoft Edge in Intune](#ingest-the-microsoft-edge-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="8392f-342">Before using the steps in this section you must complete the steps described in [Ingest the Microsoft Edge ADMX file into Intune](#ingest-the-microsoft-edge-admx-file-into-intune).</span></span>

1. <span data-ttu-id="8392f-343">Accedi al [portale di Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8392f-343">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="8392f-344">Seleziona **Intune** in _Tutti i servizi_ oppure cerca Intune nella casella di ricerca del portale.</span><span class="sxs-lookup"><span data-stu-id="8392f-344">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
3. <span data-ttu-id="8392f-345">Vai a **Intune**>**Configurazione del dispositivo**>**Profili**.</span><span class="sxs-lookup"><span data-stu-id="8392f-345">Go to **Intune**>**Device configuration**>**Profiles**.</span></span>
4. <span data-ttu-id="8392f-346">Seleziona il profilo "Configurazione inserita ADMX Microsoft Edge" o il nome usato per il profilo.</span><span class="sxs-lookup"><span data-stu-id="8392f-346">Select the "Microsoft Edge ADMX ingested configuration" profile or the name you used for the profile.</span></span>
5. <span data-ttu-id="8392f-347">Per aggiungere le impostazioni dei criteri di Microsoft Edge, devi aprire **Impostazioni OMA-URI personalizzate**.</span><span class="sxs-lookup"><span data-stu-id="8392f-347">To add Microsoft Edge policy settings, you have to open **Custom OMA-URI Settings**.</span></span> <span data-ttu-id="8392f-348">In **Gestisci**, fai clic su **Proprietà**, quindi su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="8392f-348">Under **Manage**, click **Properties**, and then click **Settings**.</span></span>

    ![Configurare le impostazioni del profilo](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. <span data-ttu-id="8392f-350">In **Impostazioni OMA-URI personalizzate** fai clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8392f-350">On **Custom OMA-URI Settings**, click **Add**.</span></span>

    ![Aggiungere una riga alle impostazioni URI OMA](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. <span data-ttu-id="8392f-352">In **Aggiungi riga** specifica le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8392f-352">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="8392f-353">**Nome**: immetti un nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="8392f-353">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="8392f-354">Si consiglia di usare il nome del criterio da configurare.</span><span class="sxs-lookup"><span data-stu-id="8392f-354">We suggest using the policy name you want to configure.</span></span> <span data-ttu-id="8392f-355">Per questo esempio, usa "ShowHomeButton".</span><span class="sxs-lookup"><span data-stu-id="8392f-355">For this example, use "ShowHomeButton".</span></span>
   - <span data-ttu-id="8392f-356">**Descrizione**: (facoltativo) immetti una descrizione per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="8392f-356">**Description** (Optional): Enter a description for the setting.</span></span>
   - <span data-ttu-id="8392f-357">**OMA-URI**: immetti il valore URI OMA per il criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-357">**OMA-URI**: Enter the OMA-URI for the policy.</span></span> <span data-ttu-id="8392f-358">Usando il criterio "ShowHomeButton" come esempio, usa questa stringa: "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"</span><span class="sxs-lookup"><span data-stu-id="8392f-358">Using the for "ShowHomeButton" policy as an example, use this string: "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"</span></span>
   - <span data-ttu-id="8392f-359">**Tipo di dati**: seleziona il tipo di dati delle impostazioni del criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-359">**Data type**: Select the policy settings data type.</span></span> <span data-ttu-id="8392f-360">Per il criterio "ShowHomeButton", usa "String"</span><span class="sxs-lookup"><span data-stu-id="8392f-360">For the "ShowHomeButton" policy, use "String"</span></span>
   - <span data-ttu-id="8392f-361">**Valore**: immetti l'impostazione che si desidera configurare per il criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-361">**Value**: Enter the setting that you want to configure for the policy.</span></span> <span data-ttu-id="8392f-362">Per "ShowHomeButton", ad esempio, immettere “\<enabled/>”.</span><span class="sxs-lookup"><span data-stu-id="8392f-362">For "ShowHomeButton" example, enter "\<enabled/>".</span></span> <span data-ttu-id="8392f-363">Nella schermata seguente vengono visualizzate le impostazioni per configurare un criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-363">The following screenshot shows the settings for configuring a policy.</span></span>

        ![Aggiungere una riga, impostazioni OMA-URI personalizzate](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - <span data-ttu-id="8392f-365">Fai clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8392f-365">Click **OK**.</span></span>

8. <span data-ttu-id="8392f-366">In **Impostazioni OMA-URI personalizzate** fai clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8392f-366">On **Custom OMA-URI Settings**, click **OK**.</span></span>
9. <span data-ttu-id="8392f-367">Nel profilo "**Configurazione inserita ADMX Microsoft Edge - Proprietà**" (o nel nome usato), fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8392f-367">On the "**Microsoft Edge ADMX ingested configuration - Properties**" profile (or the name you used), click **Save**.</span></span>

<span data-ttu-id="8392f-368">Dopo aver creato il profilo e impostato le proprietà, devi [assegnare il profilo in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="8392f-368">After the profile is created and the properties set, you have to [assign the profile in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

#### <span data-ttu-id="8392f-369">Verificare che il criterio sia stato impostato</span><span class="sxs-lookup"><span data-stu-id="8392f-369">Confirm that the policy was set</span></span>

<span data-ttu-id="8392f-370">Usa la procedura seguente per verificare che i criteri di Microsoft Edge usino il profilo creato.</span><span class="sxs-lookup"><span data-stu-id="8392f-370">Use the following steps to confirm that the Microsoft Edge policy is using the profile you created.</span></span> <span data-ttu-id="8392f-371">Concedi a Microsoft Intune tempo per propagare il criterio a un dispositivo assegnato nell'esempio di profilo "Configurazione inserita Microsoft Edge ADMX".</span><span class="sxs-lookup"><span data-stu-id="8392f-371">(Give Microsoft Intune time to propagate the policy to a device you assigned in the "Microsoft Edge ADMX ingested configuration" profile example.)</span></span>

1. <span data-ttu-id="8392f-372">Apri Microsoft Edge e vai a *edge://policy*.</span><span class="sxs-lookup"><span data-stu-id="8392f-372">Open Microsoft Edge and go to *edge://policy*.</span></span>
2. <span data-ttu-id="8392f-373">Nella pagina **Criteri** verifica se il criterio impostato nel profilo è elencato.</span><span class="sxs-lookup"><span data-stu-id="8392f-373">On the **Policies** page, see if the policy you set in the profile is listed.</span></span>
3. <span data-ttu-id="8392f-374">Se il criterio non viene visualizzato, vedi [Diagnosticare gli errori di MDM in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) oppure [Risoluzione dei problemi relativi alle impostazioni dei criteri](#troubleshoot-a-policy-setting).</span><span class="sxs-lookup"><span data-stu-id="8392f-374">If your policy isn't shown, see [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) or [Troubleshoot a policy setting](#troubleshoot-a-policy-setting).</span></span>

#### <span data-ttu-id="8392f-375">Risoluzione dei problemi relativi alle impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="8392f-375">Troubleshoot a policy setting</span></span>

<span data-ttu-id="8392f-376">Se un criterio di Microsoft Edge non ha effetto, prova a eseguire queste le operazioni:</span><span class="sxs-lookup"><span data-stu-id="8392f-376">If a Microsoft Edge policy isn’t taking effect, try the following steps:</span></span>

<span data-ttu-id="8392f-377">Apri la pagina *edge://policy* nel dispositivo di destinazione (un dispositivo a cui hai assegnato il profilo in Microsoft Intune) e cerca il criterio.</span><span class="sxs-lookup"><span data-stu-id="8392f-377">Open the *edge://policy* page on the target device (a device you assigned the profile to in Microsoft Intune) and search for the policy.</span></span> <span data-ttu-id="8392f-378">Se il criterio non è presente nella pagina *edge://policy*, prova le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8392f-378">If the policy isn’t on the *edge://policy* page, try the following:</span></span>

- <span data-ttu-id="8392f-379">Verificare che il criterio sia nel Registro di sistema e che sia corretto.</span><span class="sxs-lookup"><span data-stu-id="8392f-379">Check that the policy is in the registry and is correct.</span></span> <span data-ttu-id="8392f-380">Nel dispositivo di destinazione apri l'editor del Registro di sistema di Windows 10 (**tasto Windows + r**, immetti "*regedit*" e quindi premi **Invio**.) Verifica che il criterio sia definito in modo corretto nel percorso *\Software\Policies\ Microsoft\Edge*.</span><span class="sxs-lookup"><span data-stu-id="8392f-380">On the target device open the Windows 10 Registry Editor (**Windows key + r**, enter “*regedit*” and then press **Enter**.) Check that the policy is correctly defined in the *\Software\Policies\ Microsoft\Edge* path.</span></span> <span data-ttu-id="8392f-381">Se non trovi il criterio nel percorso previsto, il criterio non è stato inserito correttamente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8392f-381">If you don’t find the policy in the expected path, then the policy wasn’t pushed to the device correctly.</span></span>
- <span data-ttu-id="8392f-382">Verifica che il percorso URI OMA sia corretto e che il valore sia una stringa XML valida.</span><span class="sxs-lookup"><span data-stu-id="8392f-382">Check that the OMA-URI path is correct, and the value is a valid XML string.</span></span> <span data-ttu-id="8392f-383">Se uno di questi elementi non è corretto, il criterio non viene inserito nel dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8392f-383">If either of these are incorrect the policy won’t be pushed to the target device.</span></span>

<span data-ttu-id="8392f-384">Per altri suggerimenti per la risoluzione dei problemi, vedi [Configurare Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/setup-steps) e [Sincronizzare dispositivi](https://docs.microsoft.com/intune/remote-actions/device-sync).</span><span class="sxs-lookup"><span data-stu-id="8392f-384">For more trouble shooting tips, see [Set up Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/setup-steps) and [Sync devices](https://docs.microsoft.com/intune/remote-actions/device-sync).</span></span>

## <span data-ttu-id="8392f-385">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8392f-385">See also</span></span>

- [<span data-ttu-id="8392f-386">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="8392f-386">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="8392f-387">Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8392f-387">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="8392f-388">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="8392f-388">Mobile device management</span></span>](https://docs.microsoft.com/windows/client-management/mdm/)
- [<span data-ttu-id="8392f-389">Usare le impostazioni personalizzate per i dispositivi Windows 10 in Intune</span><span class="sxs-lookup"><span data-stu-id="8392f-389">Use custom settings for Windows 10 devices in Intune</span></span>](https://docs.microsoft.com/intune/configuration/custom-settings-windows-10)
- [<span data-ttu-id="8392f-390">Configurazione dei criteri delle app Win32 e Desktop Bridge</span><span class="sxs-lookup"><span data-stu-id="8392f-390">Win32 and Desktop Bridge app policy configuration</span></span>](https://docs.microsoft.com/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [<span data-ttu-id="8392f-391">Informazioni sui criteri con backup ADMX</span><span class="sxs-lookup"><span data-stu-id="8392f-391">Understanding ADMX-backed policies</span></span>](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies)
