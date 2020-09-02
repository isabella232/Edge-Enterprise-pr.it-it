---
title: Microsoft Edge e download di contenuto misto
ms.author: kele
author: dan-wesley
manager: srugh
ms.date: 04/30/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge e download di contenuto misto
ms.openlocfilehash: 57da17a8684b97aad88e7837ff9d070f6862357b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980211"
---
# <span data-ttu-id="c5aa8-103">Informazioni su Microsoft Edge e i download di contenuto misto</span><span class="sxs-lookup"><span data-stu-id="c5aa8-103">Learn about Microsoft Edge and mixed content downloads</span></span>

<span data-ttu-id="c5aa8-104">Questo articolo illustra i download di contenuto misto e il modo in cui Microsoft Edge li gestisce.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-104">This article explains mixed content downloads and how Microsoft Edge handles them.</span></span>

>[!NOTE]
><span data-ttu-id="c5aa8-105">Questo articolo si applica a Microsoft Edge versione 85 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <span data-ttu-id="c5aa8-106">Cosa sono i download di contenuto misto?</span><span class="sxs-lookup"><span data-stu-id="c5aa8-106">What are mixed content downloads?</span></span>

<span data-ttu-id="c5aa8-107">Un download di contenuto misto si verifica quando si avvia il download da una pagina HTML che è stata caricata tramite una connessione HTTPS sicura, ma si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5aa8-107">A mixed content download happens when you start a download from an HTML page that was loaded over a secure HTTPS connection, but one of the following conditions exists:</span></span>

- <span data-ttu-id="c5aa8-108">Uno o più dei reindirizzamenti del percorso di download sono stati caricati tramite una connessione HTTP non sicura.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-108">One or more of the download location's redirects was loaded over an insecure HTTP connection.</span></span>
- <span data-ttu-id="c5aa8-109">Il percorso di download finale è stato caricato tramite una connessione HTTP non sicura.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-109">The final download location was loaded over an insecure HTTP connection.</span></span>

<span data-ttu-id="c5aa8-110">Entrambi gli scenari sono contenuti misti perché la richiesta è stata eseguita usando il protocollo HTTPS sicuro e sia il contenuto HTTP che quello HTTPS è coinvolto nel raggiungimento della destinazione finale per il download.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-110">Either scenario is a mixed content because the request was made using secure HTTPS and both HTTP and HTTPS content are involved in reaching the final download destination.</span></span> <span data-ttu-id="c5aa8-111">I browser moderni visualizzano avvisi su questo tipo di contenuto per indicare agli utenti che questo download potrebbe essere trasferito in modo non sicuro, anche se la pagina originale a cui si ha avuto accesso è sicura.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-111">Modern browsers display warnings about this type of content to indicate to the user that this download may be transferred insecurely even though the original page accessed was secure.</span></span>

## <span data-ttu-id="c5aa8-112">Avvisi download e opzioni utente</span><span class="sxs-lookup"><span data-stu-id="c5aa8-112">Download warnings and user options</span></span>

<span data-ttu-id="c5aa8-113">L'avviso download garantisce che gli utenti sappiano che il file scaricato potrebbe essere letto da utenti malintenzionati nella rete.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-113">The download warning ensures that users know that the file they're downloading could be read by malicious attackers on their network.</span></span> <span data-ttu-id="c5aa8-114">Questo avviso consente a un utente di prendere una decisione ponderata sull'eventuale download del file.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-114">This warning lets a user make an informed decision on whether to download the file.</span></span>

<span data-ttu-id="c5aa8-115">In Microsoft Edge i download di contenuto misto verranno bloccati, ma gli utenti possono ignorare e scaricare il file, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-115">In Microsoft Edge, mixed content downloads will be blocked but users can override and download the file if they want to.</span></span> <span data-ttu-id="c5aa8-116">Microsoft Edge prevede di iniziare a bloccare i download di file eseguibili con contenuto misto a partire da Microsoft Edge versione 85 e bloccherà diversi tipi di file nei rilasci futuri.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-116">Microsoft Edge plans on starting to block mixed content executable file downloads starting with Microsoft Edge version 85 and will block different filetypes in future releases.</span></span>

> [!NOTE]
> <span data-ttu-id="c5aa8-117">La distribuzione di questa funzionalità è soggetta a modifiche in base alla programmazione del rilascio e al feedback degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-117">Deployment of this feature is subject to change based on release schedule and user feedback.</span></span>

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

<span data-ttu-id="c5aa8-118">Nella barra di download il messaggio di avviso del blocco avrà l'aspetto seguente.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-118">In the download shelf, the block warning message looks like the example in the next screenshot.</span></span>

 ![Avviso contenuto misto nella barra di download](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

<span data-ttu-id="c5aa8-120">Nella pagina di download l’avviso di blocco avrà l’aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="c5aa8-120">On the download page, the block warning looks like the following screenshot example:</span></span>

 ![Richiesta di override del contenuto misto](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

<span data-ttu-id="c5aa8-122">Se un utente decide di conservare il download, viene richiesto di confermare l'azione.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-122">If a user decides to keep the download, they are prompted to confirm their action.</span></span> <span data-ttu-id="c5aa8-123">La schermata seguente mostra un esempio di richiesta di conferma.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-123">The next screenshot shows an example of this confirmation prompt.</span></span>

 ![Scegli Modalità Internet Explorer](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## <span data-ttu-id="c5aa8-125">Criteri di supporto</span><span class="sxs-lookup"><span data-stu-id="c5aa8-125">Supporting policies</span></span>

<span data-ttu-id="c5aa8-126">Per le aziende che desiderano escludere il blocco del contenuto misto da siti Web specifici, è possibile usare il criterio [InsecureContentAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#insecurecontentallowedforurls).</span><span class="sxs-lookup"><span data-stu-id="c5aa8-126">Enterprises that want to exclude mixed content blocking from specific websites can use the [InsecureContentAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#insecurecontentallowedforurls) policy to do so.</span></span>

## <span data-ttu-id="c5aa8-127">Licenza dei contenuti</span><span class="sxs-lookup"><span data-stu-id="c5aa8-127">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="c5aa8-128">Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="c5aa8-128">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="c5aa8-129">La pagina originale è disponibile [qui](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content).</span><span class="sxs-lookup"><span data-stu-id="c5aa8-129">The original page can be found [here](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="c5aa8-130">Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-130">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="c5aa8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5aa8-131">See also</span></span>

- [<span data-ttu-id="c5aa8-132">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="c5aa8-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
