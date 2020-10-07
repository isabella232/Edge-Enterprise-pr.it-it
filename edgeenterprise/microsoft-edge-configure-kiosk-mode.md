---
title: Configurare la modalità tutto schermo di Microsoft Edge
ms.author: aguta
author: aguta
manager: srugh
ms.date: 10/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare la modalità tutto schermo di Microsoft Edge
ms.openlocfilehash: 799b3dd4b7fc96f0b8e5cb718bca98fd4f38ec15
ms.sourcegitcommit: 78905f66f4a6590a57c8f2bf808af92106b62996
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "11094863"
---
# <span data-ttu-id="924fe-103">Configurare la modalità tutto schermo di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="924fe-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="924fe-104">In questo articolo viene descritto come configurare le opzioni della modalità tutto schermo di Microsoft Edge che è possibile provare.</span><span class="sxs-lookup"><span data-stu-id="924fe-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="924fe-105">Verrà anche descritta una roadmap di funzionalità che abbiamo come obiettivo.</span><span class="sxs-lookup"><span data-stu-id="924fe-105">There's also a roadmap of features we are targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="924fe-106">Questo articolo si applica a Microsoft Edge versione 87 o successiva.</span><span class="sxs-lookup"><span data-stu-id="924fe-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="924fe-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="924fe-107">Overview</span></span>

<span data-ttu-id="924fe-108">La modalità tutto schermo di Microsoft Edge offre due esperienze di blocco del browser, in modo che le organizzazioni possano creare, gestire e fornire la migliore esperienza ai propri clienti.</span><span class="sxs-lookup"><span data-stu-id="924fe-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="924fe-109">Sono disponibili le seguenti esperienze di blocco:</span><span class="sxs-lookup"><span data-stu-id="924fe-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="924fe-110">L'esperienza di segnaletica digitale/interattiva mostra un sito specifico in modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="924fe-110">The Digital/Interactive signage experience displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="924fe-111">L'esperienza di esplorazione pubblica esegue una versione multi-scheda limitata di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="924fe-111">The public-browsing experience runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="924fe-112">Entrambe le esperienze eseguono una sessione di Microsoft Edge in modalità InPrivate, che protegge i dati dell'utente.</span><span class="sxs-lookup"><span data-stu-id="924fe-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="924fe-113">Configurare la modalità tutto schermo di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="924fe-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="924fe-114">È ora disponibile un set iniziale di funzionalità della modalità tutto schermo da testare con il Canale Microsoft Edge Canary, versione 87.</span><span class="sxs-lookup"><span data-stu-id="924fe-114">An initial set of kiosk mode features are now available to test with Microsoft Edge Canary Channel, version 87.</span></span> <span data-ttu-id="924fe-115">È possibile scaricare Microsoft Edge Canary dalla pagina [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download).</span><span class="sxs-lookup"><span data-stu-id="924fe-115">You can download Microsoft Edge Canary from the [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) page.</span></span>

### <span data-ttu-id="924fe-116">Funzionalità della modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="924fe-116">Kiosk mode features</span></span>

<span data-ttu-id="924fe-117">Sono disponibili le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="924fe-117">The following features are available:</span></span>

- <span data-ttu-id="924fe-118">La navigazione InPrivate protegge i dati degli utenti eliminando i dati del browser e i download al termine della sessione.</span><span class="sxs-lookup"><span data-stu-id="924fe-118">InPrivate navigation protects user data by deleting browser data and downloads when the session ends.</span></span>
- <span data-ttu-id="924fe-119">Dei criteri per configurare Elimina download all'uscita.</span><span class="sxs-lookup"><span data-stu-id="924fe-119">A policy to configure Delete downloads on exit.</span></span>
- <span data-ttu-id="924fe-120">L’opzione per reimpostare la sessione utente dopo un determinato periodo di inattività.</span><span class="sxs-lookup"><span data-stu-id="924fe-120">The option to reset a user session after a certain period of inactivity.</span></span>
- <span data-ttu-id="924fe-121">Un set iniziale di funzionalità di blocco.</span><span class="sxs-lookup"><span data-stu-id="924fe-121">An initial set of lockdown functionality.</span></span> <span data-ttu-id="924fe-122">Sono disponibili le seguenti funzioni:</span><span class="sxs-lookup"><span data-stu-id="924fe-122">The following functions are available:</span></span>

  - <span data-ttu-id="924fe-123">Menu di scelta rapida del mouse</span><span class="sxs-lookup"><span data-stu-id="924fe-123">Mouse context menu</span></span>
  - <span data-ttu-id="924fe-124">F12 Strumenti di sviluppo</span><span class="sxs-lookup"><span data-stu-id="924fe-124">F12 Developer Tools</span></span>
  - <span data-ttu-id="924fe-125">F11 Uscita dallo schermo intero (in modalità schermo intero)</span><span class="sxs-lookup"><span data-stu-id="924fe-125">F11 Exit full screen (while in full screen mode)</span></span>
  - <span data-ttu-id="924fe-126">Blocco del set iniziale di pagine *Edge://*</span><span class="sxs-lookup"><span data-stu-id="924fe-126">Blocking of the initial set of *Edge://* pages</span></span>

> [!NOTE]
> <span data-ttu-id="924fe-127">Man mano che la modalità tutto schermo si evolve, saranno disponibili più funzionalità.</span><span class="sxs-lookup"><span data-stu-id="924fe-127">As kiosk mode evolves, more features will be available.</span></span>

## <span data-ttu-id="924fe-128">Usare le funzionalità della modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="924fe-128">Use kiosk mode features</span></span>

<span data-ttu-id="924fe-129">È possibile richiamare le funzionalità della modalità tutto schermo di Microsoft Edge con le seguenti opzioni della riga di comando per Windows 10:</span><span class="sxs-lookup"><span data-stu-id="924fe-129">You can invoke Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="924fe-130">Segnaletica digitale/interattiva in modalità tutto schermo:</span><span class="sxs-lookup"><span data-stu-id="924fe-130">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="924fe-131">Esplorazione pubblica in modalità tutto schermo:</span><span class="sxs-lookup"><span data-stu-id="924fe-131">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### <span data-ttu-id="924fe-132">Opzioni aggiuntive della riga di comando</span><span class="sxs-lookup"><span data-stu-id="924fe-132">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="924fe-133">: disabilita la prima esperienza in esecuzione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="924fe-133">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="924fe-134">: modifica il tempo (in minuti) trascorso dall'ultima attività dell’utente prima che la modalità tutto schermo di Microsoft Edge reimposti la sessione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="924fe-134">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="924fe-135">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="924fe-135">The following values are supported:</span></span>

  - <span data-ttu-id="924fe-136">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="924fe-136">Default values</span></span>
    - <span data-ttu-id="924fe-137">Schermo intero - disattivato</span><span class="sxs-lookup"><span data-stu-id="924fe-137">Full screen - turned off</span></span>
    - <span data-ttu-id="924fe-138">Esplorazione pubblica - 5 minuti</span><span class="sxs-lookup"><span data-stu-id="924fe-138">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="924fe-139">Valori consentiti</span><span class="sxs-lookup"><span data-stu-id="924fe-139">Allowed values</span></span>
    - <span data-ttu-id="924fe-140">0: spegne il timer</span><span class="sxs-lookup"><span data-stu-id="924fe-140">0 - turns off the timer</span></span>
    - <span data-ttu-id="924fe-141">1: 1440 minuti per il ripristino del timer di inattività</span><span class="sxs-lookup"><span data-stu-id="924fe-141">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="924fe-142">Microsoft Edge con accesso assegnato</span><span class="sxs-lookup"><span data-stu-id="924fe-142">Microsoft Edge with assigned access</span></span>

### <span data-ttu-id="924fe-143">Chiosco con una sola app</span><span class="sxs-lookup"><span data-stu-id="924fe-143">Single app kiosk</span></span>

<span data-ttu-id="924fe-144">Attualmente, Microsoft Edge supporta un sottogruppo delle stesse modalità tutto schermo di Microsoft Edge Legacy per accesso assegnato con sola app con le seguenti esperienze di blocco, segnaletica digitale/interattiva ed esplorazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="924fe-144">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences, Digital/Interactive signage and Public-browsing.</span></span>  

<span data-ttu-id="924fe-145">La modalità tutto schermo con accesso assegnato è al momento disponibile per essere testata con l'ultima  [build di Windows 10 Insider Preview](https://insider.windows.com/), versione 20215 o successiva, e con il  [Canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), versione 87.0.644.4 o successiva.</span><span class="sxs-lookup"><span data-stu-id="924fe-145">Kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4 or higher.</span></span>

**<span data-ttu-id="924fe-146">Come ottengo l'anteprima di Windows Insiders?</span><span class="sxs-lookup"><span data-stu-id="924fe-146">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="924fe-147">Per installare una build di Windows 10 Insider Preview su PC, seguire le istruzioni in  [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).</span><span class="sxs-lookup"><span data-stu-id="924fe-147">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="924fe-148">Chiosco con più app</span><span class="sxs-lookup"><span data-stu-id="924fe-148">Multi-app kiosk</span></span>

<span data-ttu-id="924fe-149">Microsoft Edge può essere eseguito con [accesso assegnato con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) su Windows 10, che è l'equivalente del tipo di modalità tutto schermo per l'esplorazione normale di Microsoft Edge Legacy.</span><span class="sxs-lookup"><span data-stu-id="924fe-149">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="924fe-150">Per configurare Microsoft Edge con l'accesso assegnato con più app, segui le istruzioni su come [configurare un chiosco multimediale con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span><span class="sxs-lookup"><span data-stu-id="924fe-150">To configure Microsoft Edge with multi-app assigned access follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="924fe-151">(L'AUMID per il canale Microsoft Edge Stable è **MSEdge.**)</span><span class="sxs-lookup"><span data-stu-id="924fe-151">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="924fe-152">Configurare la modalità tutto schermo di Microsoft Edge Quando usi Microsoft Edge con accesso assegnato con più app, puoi utilizzare i [criteri del browser Microsoft Edge](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies) per configurare l'esperienza di esplorazione per soddisfare i tuoi requisiti univoci.</span><span class="sxs-lookup"><span data-stu-id="924fe-152">Configure Microsoft Edge kiosk mode When using Microsoft Edge with multi-app assigned access you can use the [Microsoft Edge browser policies](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <span data-ttu-id="924fe-153">Configurare usando le impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="924fe-153">Configure using Windows Settings</span></span>

<span data-ttu-id="924fe-154">Il modo più semplice per configurare uno o due dispositivi in modalità tutto schermo con app singola è tramite le impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="924fe-154">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="924fe-155">Usa i seguenti passaggi per configurare un computer in modalità tutto schermo con app singola.</span><span class="sxs-lookup"><span data-stu-id="924fe-155">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="924fe-156">Installa l'ultima versione di Windows 10 Insider Preview, versione 20215 o successiva.</span><span class="sxs-lookup"><span data-stu-id="924fe-156">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="924fe-157">Segui le istruzioni in [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).</span><span class="sxs-lookup"><span data-stu-id="924fe-157">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="924fe-158">Installa l'ultima versione del [canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), 87.0.644.4 o successiva.</span><span class="sxs-lookup"><span data-stu-id="924fe-158">Install the latest version of [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), 87.0.644.4 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="924fe-159">Poiché è richiesta un'installazione a livello di dispositivo, è supportato solo un canale non Canary.</span><span class="sxs-lookup"><span data-stu-id="924fe-159">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="924fe-160">Dal computer di un chiosco multimediale, apri le Impostazioni di Windows e digita "chiosco" nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="924fe-160">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="924fe-161">Seleziona  **Configura un chiosco multimediale (accesso assegnato**), mostrato nella schermata successiva per aprire la finestra di dialogo per la creazione del chiosco.</span><span class="sxs-lookup"><span data-stu-id="924fe-161">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

4. <span data-ttu-id="924fe-163">Nella pagina **Configura un chiosco multimediale** , fai clic su  **Inizia**.</span><span class="sxs-lookup"><span data-stu-id="924fe-163">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

5. <span data-ttu-id="924fe-165">Digita un nome per creare un nuovo account per chiosco multimediale o scegli un account esistente dall'elenco a discesa popolato e quindi fai clic su  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924fe-165">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

6. <span data-ttu-id="924fe-167">Nella pagina **Scegli un'app chiosco multimediale** , seleziona **Microsoft Edge** e quindi fai clic su  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924fe-167">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="924fe-168">Questo si applica solo ai canali Microsoft Edge Dev, Beta e Stable.</span><span class="sxs-lookup"><span data-stu-id="924fe-168">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

7. <span data-ttu-id="924fe-170">Scegli una delle seguenti opzioni per la modalità di visualizzazione di Microsoft Edge durante l'esecuzione in modalità tutto schermo:</span><span class="sxs-lookup"><span data-stu-id="924fe-170">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="924fe-171">Segnaletica digitale/interattiva - Visualizza un sito specifico in modalità a schermo intero, con Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="924fe-171">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="924fe-172">Browser pubblico - Esegue una versione multi-scheda limitata di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="924fe-172">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

8. <span data-ttu-id="924fe-174">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924fe-174">Select **Next**.</span></span>
9. <span data-ttu-id="924fe-175">Digita l'URL da caricare all'avvio del chiosco.</span><span class="sxs-lookup"><span data-stu-id="924fe-175">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

10. <span data-ttu-id="924fe-177">Accetta il valore predefinito di 5 minuti per il tempo di inattività o fornisci un valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="924fe-177">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

11. <span data-ttu-id="924fe-179">Fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="924fe-179">Click **Next**.</span></span>
12. <span data-ttu-id="924fe-180">Chiudi la finestra **Impostazioni**  per salvare e applicare le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="924fe-180">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

13. <span data-ttu-id="924fe-182">Disconnettiti dal chiosco multimediale ed esegui l'accesso con l'account chiosco locale per convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="924fe-182">Sign off from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="924fe-183">Limitazioni funzionali</span><span class="sxs-lookup"><span data-stu-id="924fe-183">Functional limitations</span></span>

<span data-ttu-id="924fe-184">Con il rilascio della versione di anteprima della modalità tutto schermo stiamo continuando a migliorare il prodotto e aggiungere nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="924fe-184">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="924fe-185">Sebbene la modalità tutto schermo attualmente non supporti le seguenti funzionalità, stiamo lavorando sulle seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="924fe-185">Although kiosk mode doesn't currently support the following functionality, work is underway on the following features:</span></span>

- <span data-ttu-id="924fe-186">Raccolte</span><span class="sxs-lookup"><span data-stu-id="924fe-186">Collections</span></span>
- <span data-ttu-id="924fe-187">Extensions</span><span class="sxs-lookup"><span data-stu-id="924fe-187">Extensions</span></span>
- <span data-ttu-id="924fe-188">Modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="924fe-188">Internet Explorer mode</span></span>
- <span data-ttu-id="924fe-189">Windows Defender Application Guard (WDAG)</span><span class="sxs-lookup"><span data-stu-id="924fe-189">Windows Defender Application Guard (WDAG)</span></span>

## <span data-ttu-id="924fe-190">Roadmap</span><span class="sxs-lookup"><span data-stu-id="924fe-190">Roadmap</span></span>

### <span data-ttu-id="924fe-191">Alla fine di quest'anno (2020)</span><span class="sxs-lookup"><span data-stu-id="924fe-191">Later this year (2020)</span></span>

<span data-ttu-id="924fe-192">Verranno aggiunte le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="924fe-192">We'll add the following features:</span></span>

- <span data-ttu-id="924fe-193">Pulsante Termina sessione</span><span class="sxs-lookup"><span data-stu-id="924fe-193">End session button</span></span>
- <span data-ttu-id="924fe-194">Barra degli indirizzi di sola lettura</span><span class="sxs-lookup"><span data-stu-id="924fe-194">Read only address bar</span></span>  
  - <span data-ttu-id="924fe-195">Configurabile con i criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="924fe-195">Configurable with group policy</span></span>
  - <span data-ttu-id="924fe-196">Se abilitato, agli utenti verrà impedito di modificare la barra degli indirizzi e spostarsi in un'altra pagina.</span><span class="sxs-lookup"><span data-stu-id="924fe-196">When enabled, users will be prevented from editing the address bar and navigating to another page.</span></span>

- <span data-ttu-id="924fe-197">Altre funzioni di blocco:</span><span class="sxs-lookup"><span data-stu-id="924fe-197">More lockdown functions:</span></span>

  - <span data-ttu-id="924fe-198">Gli acceleratori aggiuntivi verranno bloccati (ad esempio, CTRL + N)</span><span class="sxs-lookup"><span data-stu-id="924fe-198">Additional accelerators will be blocked (for example, CTRL+N)</span></span>
  - <span data-ttu-id="924fe-199">Il menu delle impostazioni "..." abiliterà solo le opzioni richieste (ad esempio, Stampa, Guida, Feedback e Leggi ad alta voce)</span><span class="sxs-lookup"><span data-stu-id="924fe-199">The "…" settings menu will enable only required options (for example, Print, Help,  Feedback, and Read aloud)</span></span>
  - <span data-ttu-id="924fe-200">Pagine di blocco aggiuntive *edge://* (ad esempio, *edge://settings*)</span><span class="sxs-lookup"><span data-stu-id="924fe-200">Additional *edge://* pages lockdown (for example, *edge://settings*)</span></span>
  - <span data-ttu-id="924fe-201">Configurazione dell'interfaccia utente delle opzioni di stampa</span><span class="sxs-lookup"><span data-stu-id="924fe-201">Configure print options UI</span></span>
  - <span data-ttu-id="924fe-202">Limitazione di esplorazione dei file solo alla cartella di download.</span><span class="sxs-lookup"><span data-stu-id="924fe-202">Limiting file explorer to the download folder only.</span></span>

### <span data-ttu-id="924fe-203">All'inizio del 2021</span><span class="sxs-lookup"><span data-stu-id="924fe-203">In early 2021</span></span>

<span data-ttu-id="924fe-204">Verranno aggiunte le seguenti funzionalità e supporto:</span><span class="sxs-lookup"><span data-stu-id="924fe-204">We'll add the following support and features:</span></span>

- <span data-ttu-id="924fe-205">Disponibilità generale della modalità tutto schermo di Microsoft Edge con app singola con accesso assegnato su Windows.</span><span class="sxs-lookup"><span data-stu-id="924fe-205">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows.</span></span>
- <span data-ttu-id="924fe-206">Funzionalità aggiuntive per la parità con la versione legacy di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="924fe-206">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="924fe-207">Integrazione con Intune per configurare i dispositivi con il profilo in modalità tutto schermo UX.</span><span class="sxs-lookup"><span data-stu-id="924fe-207">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>

## <span data-ttu-id="924fe-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="924fe-208">See also</span></span>

- [<span data-ttu-id="924fe-209">Configurare chioschi multimediali e firme digitali nelle edizioni desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="924fe-209">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="924fe-210">Distribuire la modalità tutto schermo di Microsoft Edge Legacy</span><span class="sxs-lookup"><span data-stu-id="924fe-210">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="924fe-211">Pianificare la distribuzione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="924fe-211">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="924fe-212">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="924fe-212">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
