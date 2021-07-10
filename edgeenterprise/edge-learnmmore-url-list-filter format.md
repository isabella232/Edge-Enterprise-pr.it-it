---
title: Formato di filtro per i criteri URL di Microsoft Edge
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Informazioni sul formato di filtro usato per i criteri URLBlocklist e URLAllowlist di Microsoft Edge.
ms.openlocfilehash: e178dad518ff4bee07bf89d9faca3231ee6cf246
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642022"
---
# <a name="filter-format-for-url-list-based-policies"></a><span data-ttu-id="35520-103">Formato di filtro per criteri basati su elenchi di URL</span><span class="sxs-lookup"><span data-stu-id="35520-103">Filter format for URL list-based policies</span></span>

<span data-ttu-id="35520-104">Questo articolo descrive il formato di filtro usato per i criteri basati su elenco per gli URL di Microsoft Edge (ad esempio [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist) e [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls).</span><span class="sxs-lookup"><span data-stu-id="35520-104">This article describes the filter format used for the Microsoft Edge URL list-based policies (For example, [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist), and [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) policies.</span></span>

> [!NOTE]
> <span data-ttu-id="35520-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="35520-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="the-filter-format"></a><span data-ttu-id="35520-106">Formato di filtro</span><span class="sxs-lookup"><span data-stu-id="35520-106">The filter format</span></span>

<span data-ttu-id="35520-107">Il formato di filtro è:</span><span class="sxs-lookup"><span data-stu-id="35520-107">The filter format is:</span></span>

```
    [scheme://][.]host[:port][/path][@query]
```

<span data-ttu-id="35520-108">I campi nel formato di filtro sono:</span><span class="sxs-lookup"><span data-stu-id="35520-108">The fields in the filter format are:</span></span>

| <span data-ttu-id="35520-109">Campo</span><span class="sxs-lookup"><span data-stu-id="35520-109">Field</span></span> | <span data-ttu-id="35520-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35520-110">Description</span></span> |
| --- | --- |
| <span data-ttu-id="35520-111">**schema** (*facoltativo*)</span><span class="sxs-lookup"><span data-stu-id="35520-111">**scheme** (*optional*)</span></span> | <span data-ttu-id="35520-112">Può essere http://, https://, ftp://, edge:// e così via.</span><span class="sxs-lookup"><span data-stu-id="35520-112">It can be http://, https://, ftp://, edge://, etc.</span></span> |
| <span data-ttu-id="35520-113">**host** (*obbligatorio*)</span><span class="sxs-lookup"><span data-stu-id="35520-113">**host** (*required*)</span></span> | <span data-ttu-id="35520-114">Deve essere un nome host valido ed è possibile utilizzare un carattere jolly ("\*").</span><span class="sxs-lookup"><span data-stu-id="35520-114">It must be a valid host name and you can use a wildcard ("\*").</span></span> <span data-ttu-id="35520-115">Per disabilitare la corrispondenza dei sottodomini, includere un punto facoltativo (".") prima di **host**.</span><span class="sxs-lookup"><span data-stu-id="35520-115">To disable subdomain matching, include an optional dot (".") before **host**.</span></span> <span data-ttu-id="35520-116">È possibile specificare un singolo indirizzo IP letterale del nome host, ma i caratteri jolly non sono supportati per un indirizzo IP letterale del nome host.</span><span class="sxs-lookup"><span data-stu-id="35520-116">A single IP Address Literal hostname may be specified, but wildcarding is not supported for an IP Address Literal hostname.</span></span> |
| <span data-ttu-id="35520-117">**porta** (*facoltativo*)</span><span class="sxs-lookup"><span data-stu-id="35520-117">**port** (*optional*)</span></span> | <span data-ttu-id="35520-118">I valori validi sono compresi tra 1 e 65535.</span><span class="sxs-lookup"><span data-stu-id="35520-118">Valid values range from 1 to 65535.</span></span> |
| <span data-ttu-id="35520-119">**percorso** (*facoltativo*)</span><span class="sxs-lookup"><span data-stu-id="35520-119">**path** (*optional*)</span></span> | <span data-ttu-id="35520-120">Puoi usare qualsiasi stringa nel percorso.</span><span class="sxs-lookup"><span data-stu-id="35520-120">You can use any string in the path.</span></span> |
| <span data-ttu-id="35520-121">**query** (*facoltativo*)</span><span class="sxs-lookup"><span data-stu-id="35520-121">**query** (*optional*)</span></span> | <span data-ttu-id="35520-122">La **query** è costituita da token chiave-valore o solo chiave separati da un simbolo ("&").</span><span class="sxs-lookup"><span data-stu-id="35520-122">The **query** is either key-value or key-only tokens separated by an ampersand ("&").</span></span> <span data-ttu-id="35520-123">Separa i token chiave-valore con un simbolo di uguale ("=").</span><span class="sxs-lookup"><span data-stu-id="35520-123">Separate key-value tokens with an equal sign ("=").</span></span> <span data-ttu-id="35520-124">Per indicare una corrispondenza di prefisso, puoi usare un asterisco ("\*") alla fine della **query**.</span><span class="sxs-lookup"><span data-stu-id="35520-124">To indicate a prefix match, you can use an asterisk ("\*") at the end of the **query**.</span></span> |

## <a name="comparing-the-filter-format-to-the-url-format"></a><span data-ttu-id="35520-125">Confronto tra il formato di filtro e il formato dell'URL</span><span class="sxs-lookup"><span data-stu-id="35520-125">Comparing the filter format to the URL format</span></span>

<span data-ttu-id="35520-126">Il formato del filtro è simile al formato dell'URL, ad eccezione delle differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="35520-126">The filter format resembles the URL format, except for the following differences:</span></span>

- <span data-ttu-id="35520-127">Se includi "user:pass", verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="35520-127">If you include "user:pass", it will be ignored.</span></span> <span data-ttu-id="35520-128">Ad esempio: http://user:pass@ftp.contoso.com/pub/example.iso.</span><span class="sxs-lookup"><span data-stu-id="35520-128">For example, http://user:pass@ftp.contoso.com/pub/example.iso.</span></span>
- <span data-ttu-id="35520-129">Se includi un identificatore di frammento ("#"), quest'ultimo e tutti gli elementi che seguono gli identificatori vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="35520-129">If you include a fragment identifier ("#"), it and everything that follows the identifier is ignored.</span></span>
- <span data-ttu-id="35520-130">Puoi usare un carattere jolly ("\*") come **host** e puoi aggiungere un punto (".") come prefisso.</span><span class="sxs-lookup"><span data-stu-id="35520-130">You can use a wildcard ("\*") as the **host** and you can prefix it with a dot (".").</span></span>
- <span data-ttu-id="35520-131">Puoi usare una barra ("/") o un punto (".") come suffisso per l'**host**.</span><span class="sxs-lookup"><span data-stu-id="35520-131">You can use a forward slash ("/") or a dot (".") as a suffix for the **host**.</span></span> <span data-ttu-id="35520-132">In questo caso, il suffisso viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="35520-132">In this case, the suffix is ignored.</span></span>

## <a name="filter-selection-criteria"></a><span data-ttu-id="35520-133">Criteri di selezione del filtro</span><span class="sxs-lookup"><span data-stu-id="35520-133">Filter selection criteria</span></span>

<span data-ttu-id="35520-134">Il filtro selezionato per un URL è la corrispondenza più specifica trovata dopo l'elaborazione delle regole di selezione del filtro seguenti:</span><span class="sxs-lookup"><span data-stu-id="35520-134">The filter selected for a URL is the most specific match found after processing the following filter selection rules:</span></span>

1. <span data-ttu-id="35520-135">I filtri con la corrispondenza **host** più lunga sono selezionati per primi.</span><span class="sxs-lookup"><span data-stu-id="35520-135">Filters with the longest **host** match are selected first.</span></span>
2. <span data-ttu-id="35520-136">Dai filtri selezionati, qualsiasi filtro con uno schema o una porta non corrispondente viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="35520-136">From the selected filters, any filter with a non-matching scheme or port is discarded.</span></span>
3. <span data-ttu-id="35520-137">Nei filtri rimanenti viene selezionato il filtro con il **percorso** corrispondente più lungo.</span><span class="sxs-lookup"><span data-stu-id="35520-137">From the remaining filters, the filter with the longest matching **path** is selected.</span></span>
4. <span data-ttu-id="35520-138">Nei filtri rimanenti viene selezionato il filtro con il set di token di query più lungo.</span><span class="sxs-lookup"><span data-stu-id="35520-138">From the remaining filters, the filter with the longest set of query tokens is selected.</span></span> <span data-ttu-id="35520-139">In questo passaggio il filtro elenco Consentiti ha la precedenza sul filtro elenco Blocca se entrambi i filtri hanno la stessa lunghezza di **percorso** e lo stesso numero di token di **query**.</span><span class="sxs-lookup"><span data-stu-id="35520-139">At this step, the allow list filter takes precedence over the block list filter if both filters have the same **path** length and number of **query** tokens.</span></span>
5. <span data-ttu-id="35520-140">Se non è presente alcun filtro valido, il sottodominio più a sinistra viene rimosso dall'**host** e il processo di selezione viene riavviato dal passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="35520-140">If there's no valid filter remaining, then the left-most subdomain is removed from **host** and the selection process starts over at step 1.</span></span> <span data-ttu-id="35520-141">L'**host** con asterisco speciale ("\*") è l'ultimo cercato e corrisponde a tutti gli host.</span><span class="sxs-lookup"><span data-stu-id="35520-141">The special asterisk ("\*") **host** is the last searched and it matches all hosts.</span></span>
6. <span data-ttu-id="35520-142">Se un filtro è disponibile, tale filtro blocca o consente la richiesta dell'URL.</span><span class="sxs-lookup"><span data-stu-id="35520-142">If a filter's available, it blocks or allows the URL request.</span></span>

   >[!NOTE]
   ><span data-ttu-id="35520-143">Il comportamento predefinito consiste nel consentire la richiesta URL se non viene trovato alcun filtro.</span><span class="sxs-lookup"><span data-stu-id="35520-143">The default behavior is to allow the URL request if no filter is matched.</span></span>

## <a name="example-filter-selection-criteria"></a><span data-ttu-id="35520-144">Criteri di selezione del filtro di esempio</span><span class="sxs-lookup"><span data-stu-id="35520-144">Example filter selection criteria</span></span>

<span data-ttu-id="35520-145">In questo esempio, quando si cerca una corrispondenza "https://sub.contoso.com/docs" la selezione del filtro sarà:</span><span class="sxs-lookup"><span data-stu-id="35520-145">In this example, when searching for a match to "https://sub.contoso.com/docs" the filter selection will:</span></span>

1. <span data-ttu-id="35520-146">Ricerca di un filtro per "sub.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="35520-146">Search for a filter for "sub.contoso.com".</span></span> <span data-ttu-id="35520-147">Se viene trovato un filtro, la ricerca passa al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="35520-147">If it finds a filter, the search moves to step 2.</span></span> <span data-ttu-id="35520-148">Se non viene trovato alcun filtro, viene eseguito un altro tentativo con "contoso.com", "com” e infine con "".</span><span class="sxs-lookup"><span data-stu-id="35520-148">If a filter isn't found, then it tries again with "contoso.com", "com", and finally "".</span></span>
2. <span data-ttu-id="35520-149">Nei filtri selezionati, quelli per cui non è presente "http" nello **schema** vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="35520-149">From the selected filters, any that don't have "http" in the **scheme** are removed.</span></span>
3. <span data-ttu-id="35520-150">Nei filtri rimanenti quelli con un numero di porta esatto diverso da "80" vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="35520-150">From the remaining filters, any that have an exact port number that isn't "80" are removed.</span></span>
4. <span data-ttu-id="35520-151">Nei filtri rimanenti, quelli per cui non è presente "/docs" come prefisso del **percorso** vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="35520-151">From the remaining filters, any that don't have "/docs" as a prefix of the **path** are removed.</span></span>
5. <span data-ttu-id="35520-152">Nei filtri rimanenti viene selezionato e applicato il filtro con il prefisso del percorso più lungo.</span><span class="sxs-lookup"><span data-stu-id="35520-152">From the remaining filters, the filter with the longest path prefix is selected and applied.</span></span> <span data-ttu-id="35520-153">Se non viene trovato alcun filtro, il processo di selezione riparte dal passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="35520-153">If a filter isn't found, the selection process starts over again at step 1.</span></span> <span data-ttu-id="35520-154">Il processo viene ripetuto con il sottodominio successivo.</span><span class="sxs-lookup"><span data-stu-id="35520-154">The process is repeated with the next subdomain.</span></span>

### <a name="additional-filter-information"></a><span data-ttu-id="35520-155">Altre informazioni sui filtri</span><span class="sxs-lookup"><span data-stu-id="35520-155">Additional filter information</span></span>

<span data-ttu-id="35520-156">Se un filtro ha un punto (".") come prefisso dell'**host**, vengono filtrate solo le corrispondenze esatte dell'**host**.</span><span class="sxs-lookup"><span data-stu-id="35520-156">If a filter has a dot (".") prefixing the **host** then only exact **host** matches are filtered.</span></span> <span data-ttu-id="35520-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="35520-157">For example:</span></span>

- <span data-ttu-id="35520-158">"contoso.com" (senza punto) corrisponde a "contoso.com", "www.contoso.com" e "sub.www.contoso.com"</span><span class="sxs-lookup"><span data-stu-id="35520-158">"contoso.com" (no dot) will match "contoso.com", "www.contoso.com", and "sub.www.contoso.com"</span></span>
- <span data-ttu-id="35520-159">".www.contoso.com" (con un punto come prefisso) corrisponde solo a "www.contoso.com"</span><span class="sxs-lookup"><span data-stu-id="35520-159">".www.contoso.com" (with a dot prefix) will only match "www.contoso.com"</span></span>

<span data-ttu-id="35520-160">È possibile utilizzare una versione standard o personalizzata dello **schema**.</span><span class="sxs-lookup"><span data-stu-id="35520-160">You can use either a standard or custom **schema**.</span></span> <span data-ttu-id="35520-161">Gli schemi standard supportati includono:</span><span class="sxs-lookup"><span data-stu-id="35520-161">Supported standard schemas include:</span></span>

- <span data-ttu-id="35520-162">_about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, and _wss_.</span><span class="sxs-lookup"><span data-stu-id="35520-162">_about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, and _wss_.</span></span>

<span data-ttu-id="35520-163">Qualsiasi altro **schema** viene considerato come **schema** personalizzato, ma sono consentiti solo i modelli _schema:\*_ e _schema://\*_.</span><span class="sxs-lookup"><span data-stu-id="35520-163">Any other **schema** is treated as a custom **schema**, but only the _schema:\*_ and _schema://\*_ patterns are allowed.</span></span> <span data-ttu-id="35520-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="35520-164">For example:</span></span>

- <span data-ttu-id="35520-165">"personalizzata:\*" o "personalizzata://\*" corrisponderà a "personalizzata:app"</span><span class="sxs-lookup"><span data-stu-id="35520-165">"custom:\*" or "custom://\*" will match "custom:app"</span></span>
- <span data-ttu-id="35520-166">"personalizzata:app" o "personalizzata://app" non sono validi</span><span class="sxs-lookup"><span data-stu-id="35520-166">"custom:app" or "custom://app" are invalid</span></span>

<span data-ttu-id="35520-167">**schema** e **host** non rispettano la distinzione tra maiuscolo e minuscole.</span><span class="sxs-lookup"><span data-stu-id="35520-167">**schema** and **host** aren't case-sensitive.</span></span> <span data-ttu-id="35520-168">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="35520-168">For example:</span></span>

- <span data-ttu-id="35520-169">Il filtro "http://contoso.com" corrisponde a "HTTP://contoso.com", "http://contoso.COM" e "http://contoso.com"</span><span class="sxs-lookup"><span data-stu-id="35520-169">"http://contoso.com" filter matches "HTTP://contoso.com", "http://contoso.COM", and "http://contoso.com"</span></span>

<span data-ttu-id="35520-170">**percorso** e **query** rispettano la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="35520-170">**path** and **query** are case-sensitive.</span></span> <span data-ttu-id="35520-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="35520-171">For example:</span></span>

- <span data-ttu-id="35520-172">Il filtro "http://contoso.com/path?query=A" non corrisponde a "http://contoso.com/Path?query=A" né a "http://contoso.com/path?Query=A".</span><span class="sxs-lookup"><span data-stu-id="35520-172">"http://contoso.com/path?query=A" filter doesn't match "http://contoso.com/Path?query=A" or "http://contoso.com/path?Query=A".</span></span> <span data-ttu-id="35520-173">Corrisponde a "http://contoso.COM/path?query=A".</span><span class="sxs-lookup"><span data-stu-id="35520-173">It does match "http://contoso.COM/path?query=A".</span></span>

## <a name="content-license"></a><span data-ttu-id="35520-174">Licenza dei contenuti</span><span class="sxs-lookup"><span data-stu-id="35520-174">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="35520-175">Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="35520-175">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="35520-176">La [pagina originale di Chromium è disponibile qui](https://www.chromium.org/administrators/url-blacklist-filter-format).</span><span class="sxs-lookup"><span data-stu-id="35520-176">The original [Chromium page can be found here](https://www.chromium.org/administrators/url-blacklist-filter-format).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="35520-177">Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.</span><span class="sxs-lookup"><span data-stu-id="35520-177">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="35520-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35520-178">See also</span></span>

- [<span data-ttu-id="35520-179">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="35520-179">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
