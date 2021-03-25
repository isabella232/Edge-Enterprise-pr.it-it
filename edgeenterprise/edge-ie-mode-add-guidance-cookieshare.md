---
title: Condivisione cookie da Microsoft Edge a Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Come condividere cookie da Microsoft Edge a Internet Explorer '
ms.openlocfilehash: d94c1337b7a3dbee789efb16e9c8b0a5ebc2c23b
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447740"
---
# <a name="cookie-sharing-from-microsoft-edge-to-internet-explorer"></a><span data-ttu-id="33f51-103">Condivisione cookie da Microsoft Edge a Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="33f51-103">Cookie sharing from Microsoft Edge to Internet Explorer</span></span>

<span data-ttu-id="33f51-104">Questo articolo spiega come configurare la condivisione dei cookie di sessione da un processo Microsoft Edge a un processo Internet Explorer, durante l'uso della modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="33f51-104">This article explains explains how to configure session cookie sharing from a Microsoft Edge process to Internet Explorer process, while using Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="33f51-105">Questo articolo si applica a Microsoft Edge versione 87 o successiva.</span><span class="sxs-lookup"><span data-stu-id="33f51-105">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33f51-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="33f51-106">Prerequisites</span></span>

- <span data-ttu-id="33f51-107">Aggiornamenti di Windows</span><span class="sxs-lookup"><span data-stu-id="33f51-107">Windows updates</span></span>

  - <span data-ttu-id="33f51-108">Windows 10 versione 2004, Windows Server versione 2004-KB4571744 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="33f51-108">Windows 10 version 2004, Windows Server version 2004 - KB4571744 or higher</span></span>
  - <span data-ttu-id="33f51-109">Windows 10 versione 1909, Windows Server versione 1909-KB4566116 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="33f51-109">Windows 10 version 1909, Windows Server version 1909 – KB4566116 or higher</span></span>
  - <span data-ttu-id="33f51-110">Windows 10 versione 1903, Windows Server versione 1903-KB4566116 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="33f51-110">Windows 10 version 1903, Windows Server version 1903 – KB4566116 or higher</span></span>
  - <span data-ttu-id="33f51-111">Windows 10 versione 1809, Windows Server versione 1809 e Windows Server 2019 - KB4571748 o successive</span><span class="sxs-lookup"><span data-stu-id="33f51-111">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4571748 or higher</span></span>
  - <span data-ttu-id="33f51-112">Windows 10 versione 1803 - KB4577032 o successive</span><span class="sxs-lookup"><span data-stu-id="33f51-112">Windows 10 version 1803 – KB4577032 or higher</span></span>

- <span data-ttu-id="33f51-113">Microsoft Edge versione 87 o successive</span><span class="sxs-lookup"><span data-stu-id="33f51-113">Microsoft Edge version 87 or later</span></span>
- <span data-ttu-id="33f51-114">[Modalità IE](./edge-ie-mode.md)  configurata con l'Elenco siti modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="33f51-114">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="33f51-115">Panoramica</span><span class="sxs-lookup"><span data-stu-id="33f51-115">Overview</span></span>

<span data-ttu-id="33f51-116">Una configurazione comune nelle grandi organizzazioni consiste nell'avere un'applicazione che funzioni in un collegamento del browser moderno su un'altra applicazione, che potrebbe essere configurata per l'apertura in modalità Internet Explorer con Single Sign On (SSO) abilitato come parte del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="33f51-116">A common configuration in large organizations is to have an application that works on a modern browser link to another application, which might be configured to open in Internet Explorer mode with Single Sign On (SSO) enabled as part of the workflow.</span></span>

<span data-ttu-id="33f51-117">Per impostazione predefinita, i processi Microsoft Edge e Internet Explorer non condividono i cookie di sessione, che in alcuni casi possono risultare inconvenienti.</span><span class="sxs-lookup"><span data-stu-id="33f51-117">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this can be inconvenient in some cases.</span></span> <span data-ttu-id="33f51-118">Ad esempio, quando un utente deve autenticarsi nuovamente in modalità Internet Explorer o quando all’uscita da una sessione di Microsoft Edge non esce dalla sessione in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="33f51-118">For example, when a user has to re-authenticate in Internet Explorer mode or when signing out of an Microsoft Edge session doesn’t sign out of the Internet Explorer mode session.</span></span> <span data-ttu-id="33f51-119">In questi scenari, è possibile configurare cookie specifici impostati da SSO per essere inviati da Microsoft Edge a Internet Explorer, in modo che l'esperienza di autenticazione diventi più fluida eliminando la necessità di eseguire nuovamente l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="33f51-119">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to re-authenticate.</span></span>

> [!NOTE]
> <span data-ttu-id="33f51-120">I cookie di sessione possono essere condivisi solo da Microsoft Edge a Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="33f51-120">Session cookies can only be shared from Microsoft Edge to Internet Explorer.</span></span> <span data-ttu-id="33f51-121">Non è possibile condividere i cookie di sessione al contrario (da Internet Explorer a Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="33f51-121">Sharing session cookies in reverse (from Internet Explorer to Microsoft Edge) isn't possible.</span></span>

## <a name="how-cookie-sharing-works"></a><span data-ttu-id="33f51-122">Funzionamento della condivisione dei cookie</span><span class="sxs-lookup"><span data-stu-id="33f51-122">How cookie sharing works</span></span>

<span data-ttu-id="33f51-123">Il linguaggio XML dell'elenco dei siti in modalità Enterprise è stato esteso in modo da consentire la condivisione di altri elementi da una sessione Microsoft Edge a Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="33f51-123">The Enterprise Mode site list XML has been extended to allow additional elements to specify cookies that need to be shared from a Microsoft Edge session with Internet Explorer.</span></span>  

<span data-ttu-id="33f51-124">La prima volta che si crea una scheda in modalità Internet Explorer in una sessione Microsoft Edge, tutti i cookie corrispondenti vengono condivisi nella sessione di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="33f51-124">The first time an Internet Explorer mode tab is created in a Microsoft Edge session, all matching cookies are shared to the Internet Explorer session.</span></span> <span data-ttu-id="33f51-125">In seguito, ogni volta che un cookie che corrisponde a una regola viene aggiunto, eliminato o modificato, viene inviato come aggiornamento della sessione di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="33f51-125">Subsequently, any time a cookie that matches a rule is added, deleted, or modified it is sent as an update to the Internet Explorer session.</span></span> <span data-ttu-id="33f51-126">Il set di cookie condivisi viene anche valutato nuovamente quando l'elenco dei siti viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="33f51-126">The set of shared cookies is also re-evaluated when the site list is updated.</span></span>

### <a name="updated-schema-elements"></a><span data-ttu-id="33f51-127">Elementi dello schema aggiornati</span><span class="sxs-lookup"><span data-stu-id="33f51-127">Updated schema elements</span></span>

<span data-ttu-id="33f51-128">La tabella seguente descrive l'elemento \<shared-cookie\> aggiunto per supportare la funzionalità di condivisione dei cookie.</span><span class="sxs-lookup"><span data-stu-id="33f51-128">The following table describes the \<shared-cookie\> element added to support the cookie sharing feature.</span></span>

| <span data-ttu-id="33f51-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="33f51-129">Element</span></span>| <span data-ttu-id="33f51-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33f51-130">Description</span></span> |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br><span data-ttu-id="33f51-131">O</span><span class="sxs-lookup"><span data-stu-id="33f51-131">OR</span></span><br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |<span data-ttu-id="33f51-132">**(Obbligatorio)** un elemento \<shared-cookie\> richiede al minimo un*dominio* (per i cookie di dominio) oppure un attributo *host* (per i cookie solo host) e un*nome* attributo.</span><span class="sxs-lookup"><span data-stu-id="33f51-132">**(Required)** A \<shared-cookie\> element requires, at minimum, a *domain* (for domain cookies) or a *host* (for host-only cookies) attribute and a *name* attribute.</span></span><br><span data-ttu-id="33f51-133">Devono corrispondere esattamente al nome e al dominio del cookie rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="33f51-133">These must be exact matches to the cookie's domain and name respectively.</span></span> <span data-ttu-id="33f51-134">**Nota:** i sottodomini non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="33f51-134">**Note** that subdomains do not match.</span></span><br><br><span data-ttu-id="33f51-135">L'attributo di *dominio* viene utilizzato per i cookie di dominio (un punto iniziale è consentito ma facoltativo).</span><span class="sxs-lookup"><span data-stu-id="33f51-135">The *domain* attribute is used for domain cookies (and a leading dot is allowed but optional).</span></span><br><span data-ttu-id="33f51-136">L'attributo *host* viene usato per i cookie solo host (un punto iniziale è un errore).</span><span class="sxs-lookup"><span data-stu-id="33f51-136">The *host* attribute is used for host-only cookies (and a leading dot is an error).</span></span> <span data-ttu-id="33f51-137">Se non si specifica nessuno dei due o entrambi, verrà restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="33f51-137">Specifying neither or both will result in an error.</span></span><br><span data-ttu-id="33f51-138">\* Un cookie è un cookie di dominio se un dominio è stato specificato nella stringa del cookie (tramite l'intestazione della risposta HTTP Set-Cookie o l'API document.cookie JS).</span><span class="sxs-lookup"><span data-stu-id="33f51-138">\* A cookie is a domain cookie if a domain was specified in the cookie string (via HTTP Set-Cookie response header or document.cookie JS API).</span></span> <span data-ttu-id="33f51-139">Un cookie di dominio si applica al dominio specificato e a tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="33f51-139">A domain cookie applies to the specified domain and all subdomains.</span></span> <span data-ttu-id="33f51-140">Se non è stato specificato un dominio nella stringa del cookie, il cookie è solo host e si applica solo all'host specifico per cui è stato impostato.</span><span class="sxs-lookup"><span data-stu-id="33f51-140">If a domain was not specified in the cookie string, the cookie is a host-only cookie and only applies to the specific host that it was set for.</span></span> <span data-ttu-id="33f51-141">Alcune classi di URL come nomi host composti da una sola parola, ad esempio http://intranetsite) e indirizzi IP come http://10.0.0.1), possono solo impostare i cookie solo host.</span><span class="sxs-lookup"><span data-stu-id="33f51-141">Note that some classes of URLs such as single-word hostnames (e.g. http://intranetsite) and IP addresses (e.g. http://10.0.0.1) can only set host-only cookies.</span></span>    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | <span data-ttu-id="33f51-142">**(Facoltativo)** è possibile specificare un *percorso* di attributo.</span><span class="sxs-lookup"><span data-stu-id="33f51-142">**(Optional)** A *path* attribute may be specified.</span></span> <span data-ttu-id="33f51-143">Se non viene specificato alcun percorso di attributo, oppure se è vuoto, i cookie che corrispondono a dominio/host e nome corrispondono al criterio, indipendentemente dal percorso (regola jolly).</span><span class="sxs-lookup"><span data-stu-id="33f51-143">If no path attribute is specified (or if the path attribute is empty), any cookies matching domain/host and name match the policy, regardless of path (wildcard rule).</span></span><br><br><span data-ttu-id="33f51-144">Se è specificato un percorso, deve essere una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="33f51-144">If a path is specified, it must be an exact match.</span></span><br><span data-ttu-id="33f51-145">Se un cookie corrisponde a una regola con un percorso, avrà la precedenza su una regola priva di percorso.</span><span class="sxs-lookup"><span data-stu-id="33f51-145">If a cookie matches a rule with a path, that takes precedence over a rule without a path.</span></span> |

#### <a name="sharing-example"></a><span data-ttu-id="33f51-146">Esempio di condivisione</span><span class="sxs-lookup"><span data-stu-id="33f51-146">Sharing example</span></span>

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## <a name="see-also"></a><span data-ttu-id="33f51-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33f51-147">See also</span></span>

- [<span data-ttu-id="33f51-148">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="33f51-148">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="33f51-149">Informazioni sui siti configurabili</span><span class="sxs-lookup"><span data-stu-id="33f51-149">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="33f51-150">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="33f51-150">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="33f51-151">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="33f51-151">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)