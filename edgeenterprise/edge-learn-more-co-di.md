---
title: ClickOnce e DirectInvoke in Microsoft Edge
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Informazioni su ClickOnce e DirectInvoke in Microsoft Edge.
ms.openlocfilehash: 3d124f141e9212ba5ab25d4b725d32add62077a3
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642052"
---
# <a name="understand-the-clickonce-and-directinvoke-features-in-microsoft-edge"></a><span data-ttu-id="d08ec-103">Informazioni sulle funzionalità ClickOnce e DirectInvoke in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d08ec-103">Understand the ClickOnce and DirectInvoke features in Microsoft Edge</span></span>

<span data-ttu-id="d08ec-104">ClickOnce e DirectInvoke sono funzionalità disponibili in Internet Explorer e Microsoft Edge (versione 45 e precedenti) che supportano l'uso di un gestore di file per scaricare i file da un sito Web.</span><span class="sxs-lookup"><span data-stu-id="d08ec-104">ClickOnce and DirectInvoke are features available in IE and Microsoft Edge (version 45 and earlier) that support the use of a file handler to download files from a website.</span></span> <span data-ttu-id="d08ec-105">Anche se servono a scopi diversi, entrambe le funzionalità consentono ai siti Web di specificare che un file richiesto per il download viene passato a un gestore di file nel dispositivo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d08ec-105">Although they serve different purposes, both features let websites specify that a file requested for download is passed to a file handler on the user's device.</span></span> <span data-ttu-id="d08ec-106">Le richieste ClickOnce vengono gestite dal gestore di file nativo in Windows.</span><span class="sxs-lookup"><span data-stu-id="d08ec-106">ClickOnce requests are handled by the native file handler in Windows.</span></span> <span data-ttu-id="d08ec-107">Le richieste DirectInvoke vengono gestite da un gestore di file registrato specificato dal sito Web che ospita il file.</span><span class="sxs-lookup"><span data-stu-id="d08ec-107">DirectInvoke requests are handled by a registered file handler specified by the website hosting the file.</span></span>

<span data-ttu-id="d08ec-108">Per altre informazioni su queste funzionalità, vedi:</span><span class="sxs-lookup"><span data-stu-id="d08ec-108">For more information about these features, see:</span></span>

- [<span data-ttu-id="d08ec-109">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="d08ec-109">ClickOnce</span></span>](/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [<span data-ttu-id="d08ec-110">DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="d08ec-110">DirectInvoke</span></span>]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> <span data-ttu-id="d08ec-111">Attualmente, Chromium non fornisce il supporto nativo per ClickOnce o DirectInvoke.</span><span class="sxs-lookup"><span data-stu-id="d08ec-111">Currently, Chromium doesn't provide native support for ClickOnce or DirectInvoke.</span></span>

## <a name="overview-prerequisites-and-process"></a><span data-ttu-id="d08ec-112">Panoramica: prerequisiti e processo</span><span class="sxs-lookup"><span data-stu-id="d08ec-112">Overview: prerequisites and process</span></span>

<span data-ttu-id="d08ec-113">Affinché ClickOnce e DirectInvoke funzionino nel modo per cui sono state progettate e le richieste arrivino in modo corretto al gestore di file, quest'ultimo deve essere registrato nel sistema operativo in modo che supporti ClickOnce o DirectInvoke.</span><span class="sxs-lookup"><span data-stu-id="d08ec-113">For ClickOnce and DirectInvoke to work as designed and for the file handler to be successfully requested, the file handler must be registered to the operating system as supporting ClickOnce or DirectInvoke.</span></span> <span data-ttu-id="d08ec-114">Questa registrazione si verifica in genere quando viene installato il sistema operativo originale o quando un nuovo programma installato richiede la possibilità di usare DirectInvoke per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="d08ec-114">This registration typically happens when the original operating system is installed or when a new program that's installed requests the ability to use DirectInvoke for updates.</span></span>

<span data-ttu-id="d08ec-115">Quando un sito Web riceve una richiesta di download che richiede ClickOnce o DirectInvoke, si verificano le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d08ec-115">When a website receives a download request that requires ClickOnce or DirectInvoke, the following actions happen:</span></span>

- <span data-ttu-id="d08ec-116">Il sito Web richiede che il browser usi un gestore di file specificato.</span><span class="sxs-lookup"><span data-stu-id="d08ec-116">The website requests that the browser use a specified file handler.</span></span>
- <span data-ttu-id="d08ec-117">Il browser controlla il Registro di sistema del sistema operativo per verificare se il gestore di file è registrato per il tipo di file richiesto.</span><span class="sxs-lookup"><span data-stu-id="d08ec-117">The browser checks the operating system registry to see if the file handler is registered for the requested file type.</span></span>
- <span data-ttu-id="d08ec-118">Se il gestore di file è registrato, il browser lo chiama e gli passa l'URL come argomento.</span><span class="sxs-lookup"><span data-stu-id="d08ec-118">If the file handler is registered, the browser calls the file handler and passes the URL as an argument to the file handler.</span></span>
- <span data-ttu-id="d08ec-119">Il gestore di file elabora l'URL e scarica il file.</span><span class="sxs-lookup"><span data-stu-id="d08ec-119">The file handler processes the URL and downloads the file.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d08ec-120">L'URL viene usato per determinare l'origine del file, nonché i parametri da usare per l'accesso al file.</span><span class="sxs-lookup"><span data-stu-id="d08ec-120">The URL is used to determine the source of the file, as well as any parameters to use when accessing the file.</span></span>  <span data-ttu-id="d08ec-121">Ad esempio: endpoint, un manifesto oppure metadati.</span><span class="sxs-lookup"><span data-stu-id="d08ec-121">For example: endpoints, a manifest, or metadata.</span></span>

## <a name="use-cases"></a><span data-ttu-id="d08ec-122">Casi d'uso</span><span class="sxs-lookup"><span data-stu-id="d08ec-122">Use cases</span></span>

<span data-ttu-id="d08ec-123">I seguenti casi d'uso sono rappresentativi.</span><span class="sxs-lookup"><span data-stu-id="d08ec-123">The following use cases are representative.</span></span>

<span data-ttu-id="d08ec-124">Puoi usare ClickOnce per distribuire e aggiornare facilmente il software nei dispositivi con un'interazione utente minima.</span><span class="sxs-lookup"><span data-stu-id="d08ec-124">You can use ClickOnce to easily deploy and update software on devices with minimal user interaction.</span></span> <span data-ttu-id="d08ec-125">Gli utenti possono installare ed eseguire un'applicazione Windows facendo clic su un collegamento in una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="d08ec-125">Users can install and run a Windows application by clicking a link in a web page.</span></span> <span data-ttu-id="d08ec-126">Se configurata correttamente, l'applicazione ClickOnce può installare programmi senza che gli utenti impostino le configurazioni per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="d08ec-126">If configured correctly, the ClickOnce application can install programs without having users set configurations for the installer.</span></span> <span data-ttu-id="d08ec-127">Sono inclusi i percorsi dei file, le opzioni da installare e così via.</span><span class="sxs-lookup"><span data-stu-id="d08ec-127">For example, file locations, what options to install, and so on.</span></span>

<span data-ttu-id="d08ec-128">I casi d'uso di DirectInvoke dipendono dalla finalità del sito Web che richiede DirectInvoke.</span><span class="sxs-lookup"><span data-stu-id="d08ec-128">DirectInvoke use cases depend on the intent of the website requesting DirectInvoke.</span></span> <span data-ttu-id="d08ec-129">Ad esempio, la funzionalità di modifica dei file in collaborazione di Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="d08ec-129">For example, the collaborative file-editing feature of Microsoft Word.</span></span> <span data-ttu-id="d08ec-130">Invece di fare clic su un collegamento e scaricare l'intera copia di un documento a cui si sta lavorando con i colleghi, DirectInvoke consente di scaricare le parti del documento che sono state modificate.</span><span class="sxs-lookup"><span data-stu-id="d08ec-130">Instead of clicking a link and downloading the entire copy of a document you're working on with your colleagues, DirectInvoke lets you download the parts of the document that have been changed.</span></span> <span data-ttu-id="d08ec-131">Questa strategia riduce la quantità di dati trasferiti e si può ridurre il tempo necessario per aprire il documento.</span><span class="sxs-lookup"><span data-stu-id="d08ec-131">This strategy reduces the amount of data transferred and can reduce the time needed to open the document.</span></span>  

## <a name="current-support-for-clickonce-and-directinvoke-in-microsoft-edge"></a><span data-ttu-id="d08ec-132">Supporto corrente per ClickOnce e DirectInvoke in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d08ec-132">Current support for ClickOnce and DirectInvoke in Microsoft Edge</span></span>

<span data-ttu-id="d08ec-133">Supporto per ClickOnce e DirectInvoke:</span><span class="sxs-lookup"><span data-stu-id="d08ec-133">Support for ClickOnce and DirectInvoke:</span></span>

- <span data-ttu-id="d08ec-134">ClickOnce e DirectInvoke sono supportati per impostazione predefinita per tutti gli utenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="d08ec-134">ClickOnce and DirectInvoke are supported out of the box for all Windows users.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d08ec-135">Gli utenti che vogliono disabilitare il supporto per ClickOnce possono andare su *edge://flags/#edge-click-once* e selezionare **Disabilita** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d08ec-135">Users that want to disable ClickOnce support can go to *edge://flags/#edge-click-once* and select **Disabled** from the dropdown list.</span></span> <span data-ttu-id="d08ec-136">Fai clic su **Riavvia** per riavviare il browser.</span><span class="sxs-lookup"><span data-stu-id="d08ec-136">You'll have to **Restart** the browser.</span></span>

- <span data-ttu-id="d08ec-137">ClickOnce e DirectInvoke non sono supportate in nessuna piattaforma diversa da Windows.</span><span class="sxs-lookup"><span data-stu-id="d08ec-137">ClickOnce and DirectInvoke aren't supported on any platforms other than Windows.</span></span>

## <a name="clickonce-and-directinvoke-file-handling-security"></a><span data-ttu-id="d08ec-138">Sicurezza per la gestione dei file con ClickOnce e DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="d08ec-138">ClickOnce and DirectInvoke file handling security</span></span>

<span data-ttu-id="d08ec-139">ClickOnce e DirectInvoke sono funzioni protette dal servizio di analisi della reputazione URL di Microsoft Defender SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="d08ec-139">ClickOnce and DirectInvoke are protected by Microsoft Defender SmartScreen's URL reputation scanning service.</span></span>

<span data-ttu-id="d08ec-140">Se una richiesta ClickOnce o DirectInvoke è contrassegnata dal servizio di reputazione URL di Microsoft Defender SmartScreen come non sicura, agli utenti per cui ClickOnce o DirectInvoke è abilitata vengono visualizzate due finestre popup.</span><span class="sxs-lookup"><span data-stu-id="d08ec-140">If a ClickOnce or a DirectInvoke request is flagged by the Microsoft Defender SmartScreen URL reputation service as unsafe, users with ClickOnce or DirectInvoke enabled will see two popups.</span></span>

<span data-ttu-id="d08ec-141">Nella prima finestra viene chiesto all'utente se vuole aprire il file.</span><span class="sxs-lookup"><span data-stu-id="d08ec-141">The first popup asks the user if they want to open the file.</span></span> <span data-ttu-id="d08ec-142">Questa finestra viene visualizzata indipendentemente dal fatto che il file sia stato contrassegnato come sicuro o non sicuro.</span><span class="sxs-lookup"><span data-stu-id="d08ec-142">This popup is displayed regardless of whether the file was flagged as safe or unsafe.</span></span> <span data-ttu-id="d08ec-143">L'utente può selezionare i campi **Segnala file come non sicuro**, **Annulla** per annullare la richiesta o fare clic su **Apri** per continuare.</span><span class="sxs-lookup"><span data-stu-id="d08ec-143">The user can **Report the file as unsafe**, **Cancel** the request, or click **Open** to continue.</span></span>

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

<span data-ttu-id="d08ec-145">Se l'utente tenta di aprire il file e il file è stato contrassegnato come non sicuro, viene visualizzata una seconda finestra popup.</span><span class="sxs-lookup"><span data-stu-id="d08ec-145">If the user tries to open the file, and the file was flagged as unsafe, a second popup is displayed.</span></span>  <span data-ttu-id="d08ec-146">In tale finestra si avvisa l'utente che il file è stato contrassegnato come non sicuro e si chiede se desidera scaricare il file.</span><span class="sxs-lookup"><span data-stu-id="d08ec-146">This popup warns the user that the file was flagged as unsafe, and asks them if they're sure they want to download the file.</span></span>

<span data-ttu-id="d08ec-147">La seconda finestra popup viene visualizzata solo se:</span><span class="sxs-lookup"><span data-stu-id="d08ec-147">The second popup only shows up if:</span></span>

- <span data-ttu-id="d08ec-148">il file è un file ClickOnce o DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="d08ec-148">the file is a ClickOnce or DirectInvoke file</span></span>
- <span data-ttu-id="d08ec-149">ClickOnce o DirectInvoke sono abilitate</span><span class="sxs-lookup"><span data-stu-id="d08ec-149">ClickOnce or DirectInvoke are enabled</span></span>
- <span data-ttu-id="d08ec-150">il file è contrassegnato come non sicuro</span><span class="sxs-lookup"><span data-stu-id="d08ec-150">the file is flagged as unsafe</span></span>

 ![Prompt per aprire un file non sicuro](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> <span data-ttu-id="d08ec-152">Se ClickOnce o DirectInvoke sono disabilitate, i file richiesti vengono considerati come download regolari e, se contrassegnati come non sicuri, verranno considerati tali.</span><span class="sxs-lookup"><span data-stu-id="d08ec-152">If ClickOnce or DirectInvoke are disabled, requested files are treated as regular downloads and if flagged as unsafe, will be marked as unsafe.</span></span> <span data-ttu-id="d08ec-153">Questo è coerente con il trattamento di altri download non sicuri.</span><span class="sxs-lookup"><span data-stu-id="d08ec-153">This is consistent with the treatment of other unsafe downloads.</span></span>

## <a name="clickonce-and-directinvoke-policies"></a><span data-ttu-id="d08ec-154">Criteri di ClickOnce e DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="d08ec-154">ClickOnce and DirectInvoke policies</span></span>

<span data-ttu-id="d08ec-155">Esistono due criteri di gruppo che è possibile usare per abilitare o disabilitare ClickOnce e DirectInvoke per gli utenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="d08ec-155">There are two group policies that you can use to enable or disable ClickOnce and DirectInvoke for enterprise users.</span></span> <span data-ttu-id="d08ec-156">I due criteri sono [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled) e [DirectInvokeEnabled](./microsoft-edge-policies.md#directinvokeenabled).</span><span class="sxs-lookup"><span data-stu-id="d08ec-156">These two policies are [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled) and [DirectInvokeEnabled](./microsoft-edge-policies.md#directinvokeenabled).</span></span> <span data-ttu-id="d08ec-157">Questi due criteri sono contrassegnati nell'Editor Criteri di gruppo come "Consenti agli utenti di aprire file con il protocollo ClickOnce" e "Consenti agli utenti di aprire i file usando il protocollo DirectInvoke".</span><span class="sxs-lookup"><span data-stu-id="d08ec-157">These two policies are labeled in the Group Policy Editor as "Allow users to open files using the ClickOnce protocol" and "Allow users to open files using the DirectInvoke protocol" respectively.</span></span>

## <a name="clickonce-and-directinvoke-behavior"></a><span data-ttu-id="d08ec-158">Comportamento di ClickOnce e DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="d08ec-158">ClickOnce and DirectInvoke behavior</span></span>

<span data-ttu-id="d08ec-159">Gli esempi seguenti mostrano la gestione dei file quando ClickOnce e DirectInvoke sono abilitate o disabilitate.</span><span class="sxs-lookup"><span data-stu-id="d08ec-159">The following examples show file handling when ClickOnce and DirectInvoke are enabled or disabled.</span></span>

### <a name="clickonce-enabled"></a><span data-ttu-id="d08ec-160">ClickOnce abilitata</span><span class="sxs-lookup"><span data-stu-id="d08ec-160">ClickOnce enabled</span></span>

1. <span data-ttu-id="d08ec-161">Un utente apre un collegamento a una pagina che richiede il supporto di ClickOnce e riceve il prompt visualizzato nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="d08ec-161">A user opens a link to a page that requests ClickOnce support and gets the prompt in the next screenshot.</span></span>

   ![Prompt per aprire un file non sicuro](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. <span data-ttu-id="d08ec-163">Dopo che l'utente fa clic su **Apri**, ClickOnce tenta di avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d08ec-163">After the user clicks **Open**, ClickOnce attempts to launch the application.</span></span>

   ![ClickOnce tenta di avviare l'applicazione](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. <span data-ttu-id="d08ec-165">Dopo che l'utente fa clic su **Apri**, nel browser viene visualizzata una finestra popup che chiede all'utente se è sicuro di installare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d08ec-165">After the user clicks **Open**, the browser shows a popup that asks the user if they're sure they want to install the application.</span></span>

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > <span data-ttu-id="d08ec-167">L'interfaccia, la messaggistica e le opzioni visualizzate dal gestore di file ClickOnce variano a seconda del tipo e della configurazione del file a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="d08ec-167">The interface, messaging, and options shown by the ClickOnce file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <a name="clickonce-disabled"></a><span data-ttu-id="d08ec-168">ClickOnce disabilitata</span><span class="sxs-lookup"><span data-stu-id="d08ec-168">ClickOnce disabled</span></span>

1. <span data-ttu-id="d08ec-169">Quando un utente apre un collegamento a una pagina che richiede il supporto di ClickOnce, viene visualizzato un messaggio nell'area di download simile a quello nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="d08ec-169">When a user opens a link to a page that requests ClickOnce support, they will see a message in the download tray that is similar to the one in the next screenshot.</span></span>

   ![Prompt per il download del file](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### <a name="directinvoke-enabled"></a><span data-ttu-id="d08ec-171">DirectInvoke abilitata</span><span class="sxs-lookup"><span data-stu-id="d08ec-171">DirectInvoke enabled</span></span>

1. <span data-ttu-id="d08ec-172">Un utente apre un collegamento a una pagina che richiede il supporto di DirectInvoke e riceve il prompt visualizzato nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="d08ec-172">A user opens a link to a page that requests DirectInvoke support and gets the prompt in the next screenshot.</span></span>

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. <span data-ttu-id="d08ec-174">Quando l'utente fa clic su **Apri**, viene aperto il gestore di file richiesto.</span><span class="sxs-lookup"><span data-stu-id="d08ec-174">When the user clicks **Open**, the requested file handler is opened.</span></span> <span data-ttu-id="d08ec-175">In questo esempio Microsoft Word viene usato per aprire il documento visualizzato nella schermata precedente.</span><span class="sxs-lookup"><span data-stu-id="d08ec-175">In this example, Microsoft Word is used to open the document that's shown in the previous screenshot.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d08ec-176">L'interfaccia, la messaggistica e le opzioni visualizzate dal gestore di file DirectInvoke variano a seconda del tipo e della configurazione del file a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="d08ec-176">The interface, messaging, and options shown by the DirectInvoke file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <a name="directinvoke-disabled"></a><span data-ttu-id="d08ec-177">DirectInvoke disabilitata</span><span class="sxs-lookup"><span data-stu-id="d08ec-177">DirectInvoke disabled</span></span>

1. <span data-ttu-id="d08ec-178">Quando un utente apre un collegamento a una pagina che richiede il supporto di DirectInvoke, DirectInvoke si comporta in modo analogo a quando ClickOnce è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d08ec-178">When a user opens a link to a page that requests DirectInvoke support, DirectInvoke behaves the same as when ClickOnce is disabled.</span></span> <span data-ttu-id="d08ec-179">Verrà visualizzato un messaggio nell'area di download simile a quello nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="d08ec-179">They will see a message in the download tray that's similar to the one in the next screenshot.</span></span>

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## <a name="see-also"></a><span data-ttu-id="d08ec-181">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d08ec-181">See also</span></span>

- [<span data-ttu-id="d08ec-182">Sicurezza e distribuzione di ClickOnce</span><span class="sxs-lookup"><span data-stu-id="d08ec-182">ClickOnce security and deployment</span></span>](/visualstudio/deployment/clickonce-security-and-deployment)
- [<span data-ttu-id="d08ec-183">DirectInvoke in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="d08ec-183">DirectInvoke in Internet Explorer</span></span>](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/jj215788(v=vs.85))
- [<span data-ttu-id="d08ec-184">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="d08ec-184">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)