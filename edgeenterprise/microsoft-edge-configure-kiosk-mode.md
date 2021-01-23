---
title: Configurare la modalità tutto schermo di Microsoft Edge
ms.author: aguta
author: aguta
manager: srugh
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare la modalità tutto schermo di Microsoft Edge
ms.openlocfilehash: be353a0e13e9234de40296a2e8dcc31b1b800f52
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297472"
---
# <span data-ttu-id="25121-103">Configurare la modalità tutto schermo di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="25121-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="25121-104">In questo articolo viene descritto come configurare le opzioni della modalità tutto schermo di Microsoft Edge che è possibile provare.</span><span class="sxs-lookup"><span data-stu-id="25121-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="25121-105">Verrà anche descritta una roadmap di funzionalità che abbiamo come obiettivo.</span><span class="sxs-lookup"><span data-stu-id="25121-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="25121-106">Questo articolo si applica a Microsoft Edge versione 87 o successiva.</span><span class="sxs-lookup"><span data-stu-id="25121-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="25121-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="25121-107">Overview</span></span>

<span data-ttu-id="25121-108">La modalità tutto schermo di Microsoft Edge offre due esperienze di blocco del browser, in modo che le organizzazioni possano creare, gestire e fornire la migliore esperienza ai propri clienti.</span><span class="sxs-lookup"><span data-stu-id="25121-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="25121-109">Sono disponibili le seguenti esperienze di blocco:</span><span class="sxs-lookup"><span data-stu-id="25121-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="25121-110">Esperienza di **segnaletica digitale/interattiva**: mostra un sito specifico in modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="25121-110">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="25121-111">Esperienza di **esplorazione pubblica**: esegue una versione multi-scheda limitata di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="25121-111">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="25121-112">Entrambe le esperienze eseguono una sessione di Microsoft Edge in modalità InPrivate, che protegge i dati dell'utente.</span><span class="sxs-lookup"><span data-stu-id="25121-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="25121-113">Configurare la modalità tutto schermo di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="25121-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="25121-114">È disponibile un set iniziale di funzionalità della modalità tutto schermo da testare con il canale stabile Microsoft Edge, versione 87.</span><span class="sxs-lookup"><span data-stu-id="25121-114">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="25121-115">Puoi scaricare l’ultima versione da [Microsoft Edge (canale stabile ufficiale)](https://www.microsoft.com/edge).</span><span class="sxs-lookup"><span data-stu-id="25121-115">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <span data-ttu-id="25121-116">Funzionalità supportate dalla modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="25121-116">Kiosk mode supported features</span></span>

<span data-ttu-id="25121-117">La tabella seguente elenca le caratteristiche supportate dalla modalità tutto schermo.</span><span class="sxs-lookup"><span data-stu-id="25121-117">The following table lists the features supported by kiosk mode.</span></span>

|<span data-ttu-id="25121-118">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="25121-118">Feature</span></span>|<span data-ttu-id="25121-119">Segnaletica digitale/interattiva</span><span class="sxs-lookup"><span data-stu-id="25121-119">Digital\Interactive Signage</span></span>|<span data-ttu-id="25121-120">Esplorazione pubblica</span><span class="sxs-lookup"><span data-stu-id="25121-120">Public browsing</span></span>|<span data-ttu-id="25121-121">Disponibile con la versione di Microsoft Edge (e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="25121-121">Available with Microsoft Edge version (and higher)</span></span>|
|-|-|-|-|
|<span data-ttu-id="25121-122">Spostamento InPrivate</span><span class="sxs-lookup"><span data-stu-id="25121-122">InPrivate Navigation</span></span>|<span data-ttu-id="25121-123">S</span><span class="sxs-lookup"><span data-stu-id="25121-123">Y</span></span>|<span data-ttu-id="25121-124">S</span><span class="sxs-lookup"><span data-stu-id="25121-124">Y</span></span>|<span data-ttu-id="25121-125">87</span><span class="sxs-lookup"><span data-stu-id="25121-125">87</span></span>|
|<span data-ttu-id="25121-126">Reimpostazione in caso di inattività</span><span class="sxs-lookup"><span data-stu-id="25121-126">Reset on inactivity</span></span>|<span data-ttu-id="25121-127">S</span><span class="sxs-lookup"><span data-stu-id="25121-127">Y</span></span>|<span data-ttu-id="25121-128">S</span><span class="sxs-lookup"><span data-stu-id="25121-128">Y</span></span>|<span data-ttu-id="25121-129">87</span><span class="sxs-lookup"><span data-stu-id="25121-129">87</span></span>|
|<span data-ttu-id="25121-130">[Barra degli indirizzi di sola lettura](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (criterio)</span><span class="sxs-lookup"><span data-stu-id="25121-130">[Read only address bar](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="25121-131">N</span><span class="sxs-lookup"><span data-stu-id="25121-131">N</span></span>|<span data-ttu-id="25121-132">S</span><span class="sxs-lookup"><span data-stu-id="25121-132">Y</span></span> |<span data-ttu-id="25121-133">87</span><span class="sxs-lookup"><span data-stu-id="25121-133">87</span></span>|
|<span data-ttu-id="25121-134">[Eliminare i download all’uscita](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (criterio)</span><span class="sxs-lookup"><span data-stu-id="25121-134">[Delete downloads on exit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="25121-135">S</span><span class="sxs-lookup"><span data-stu-id="25121-135">Y</span></span>|<span data-ttu-id="25121-136">S</span><span class="sxs-lookup"><span data-stu-id="25121-136">Y</span></span> |<span data-ttu-id="25121-137">87</span><span class="sxs-lookup"><span data-stu-id="25121-137">87</span></span>|
|<span data-ttu-id="25121-138">F11 bloccato (entra/esci dalla modalità a schermo intero)</span><span class="sxs-lookup"><span data-stu-id="25121-138">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="25121-139">S</span><span class="sxs-lookup"><span data-stu-id="25121-139">Y</span></span> | <span data-ttu-id="25121-140">S</span><span class="sxs-lookup"><span data-stu-id="25121-140">Y</span></span> | <span data-ttu-id="25121-141">87</span><span class="sxs-lookup"><span data-stu-id="25121-141">87</span></span> |
|<span data-ttu-id="25121-142">F12 bloccato (avvia Strumenti di sviluppo)</span><span class="sxs-lookup"><span data-stu-id="25121-142">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="25121-143">S</span><span class="sxs-lookup"><span data-stu-id="25121-143">Y</span></span> | <span data-ttu-id="25121-144">S</span><span class="sxs-lookup"><span data-stu-id="25121-144">Y</span></span> | <span data-ttu-id="25121-145">87</span><span class="sxs-lookup"><span data-stu-id="25121-145">87</span></span> |
| <span data-ttu-id="25121-146">Supporto per più schede</span><span class="sxs-lookup"><span data-stu-id="25121-146">Multi tab support</span></span> | <span data-ttu-id="25121-147">N</span><span class="sxs-lookup"><span data-stu-id="25121-147">N</span></span>| <span data-ttu-id="25121-148">S</span><span class="sxs-lookup"><span data-stu-id="25121-148">Y</span></span>| <span data-ttu-id="25121-149">87</span><span class="sxs-lookup"><span data-stu-id="25121-149">87</span></span>|
|<span data-ttu-id="25121-150">Pulsante Termina sessione</span><span class="sxs-lookup"><span data-stu-id="25121-150">End session button</span></span> | <span data-ttu-id="25121-151">N</span><span class="sxs-lookup"><span data-stu-id="25121-151">N</span></span>| <span data-ttu-id="25121-152">S</span><span class="sxs-lookup"><span data-stu-id="25121-152">Y</span></span>| <span data-ttu-id="25121-153">88</span><span class="sxs-lookup"><span data-stu-id="25121-153">88</span></span>|
|<span data-ttu-id="25121-154">Tutti gli URL Microsoft Edge interni sono bloccati, ad eccezione di *edge://downloads* e *edge://print*</span><span class="sxs-lookup"><span data-stu-id="25121-154">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="25121-155">N</span><span class="sxs-lookup"><span data-stu-id="25121-155">N</span></span>|<span data-ttu-id="25121-156">S</span><span class="sxs-lookup"><span data-stu-id="25121-156">Y</span></span>|<span data-ttu-id="25121-157">88</span><span class="sxs-lookup"><span data-stu-id="25121-157">88</span></span>|
| <span data-ttu-id="25121-158">CTRL+N bloccato (apri una nuova finestra)</span><span class="sxs-lookup"><span data-stu-id="25121-158">CTRL+N blocked (open a new window)</span></span> | <span data-ttu-id="25121-159">S</span><span class="sxs-lookup"><span data-stu-id="25121-159">Y</span></span> | <span data-ttu-id="25121-160">S</span><span class="sxs-lookup"><span data-stu-id="25121-160">Y</span></span> | <span data-ttu-id="25121-161">89</span><span class="sxs-lookup"><span data-stu-id="25121-161">89</span></span> |
| <span data-ttu-id="25121-162">CTRL+T bloccato (apri una nuova scheda)</span><span class="sxs-lookup"><span data-stu-id="25121-162">CTRL+T blocked (open new tab)</span></span> | <span data-ttu-id="25121-163">N</span><span class="sxs-lookup"><span data-stu-id="25121-163">N</span></span> | <span data-ttu-id="25121-164">S</span><span class="sxs-lookup"><span data-stu-id="25121-164">Y</span></span> | <span data-ttu-id="25121-165">89</span><span class="sxs-lookup"><span data-stu-id="25121-165">89</span></span> |
|<span data-ttu-id="25121-166">Impostazioni e altro (...) mostreranno solo le opzioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="25121-166">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="25121-167">N</span><span class="sxs-lookup"><span data-stu-id="25121-167">N</span></span> |<span data-ttu-id="25121-168">S</span><span class="sxs-lookup"><span data-stu-id="25121-168">Y</span></span> |<span data-ttu-id="25121-169">89</span><span class="sxs-lookup"><span data-stu-id="25121-169">89</span></span> |

> [!NOTE]
> <span data-ttu-id="25121-170">Man mano che la modalità tutto schermo si evolve, saranno disponibili più funzionalità.</span><span class="sxs-lookup"><span data-stu-id="25121-170">As kiosk mode evolves, more features will be available.</span></span>

## <span data-ttu-id="25121-171">Usare le funzionalità della modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="25121-171">Use kiosk mode features</span></span>

<span data-ttu-id="25121-172">È possibile richiamare le funzionalità della modalità tutto schermo di Microsoft Edge con le seguenti opzioni della riga di comando per Windows 10:</span><span class="sxs-lookup"><span data-stu-id="25121-172">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="25121-173">Segnaletica digitale/interattiva in modalità tutto schermo:</span><span class="sxs-lookup"><span data-stu-id="25121-173">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="25121-174">Esplorazione pubblica in modalità tutto schermo:</span><span class="sxs-lookup"><span data-stu-id="25121-174">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### <span data-ttu-id="25121-175">Opzioni aggiuntive della riga di comando</span><span class="sxs-lookup"><span data-stu-id="25121-175">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="25121-176">: disabilita la prima esperienza in esecuzione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="25121-176">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="25121-177">: modifica il tempo (in minuti) trascorso dall'ultima attività dell’utente prima che la modalità tutto schermo di Microsoft Edge reimposti la sessione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="25121-177">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="25121-178">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="25121-178">The following values are supported:</span></span>

  - <span data-ttu-id="25121-179">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="25121-179">Default values</span></span>
    - <span data-ttu-id="25121-180">Schermo intero - disattivato</span><span class="sxs-lookup"><span data-stu-id="25121-180">Full screen - turned off</span></span>
    - <span data-ttu-id="25121-181">Esplorazione pubblica - 5 minuti</span><span class="sxs-lookup"><span data-stu-id="25121-181">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="25121-182">Valori consentiti</span><span class="sxs-lookup"><span data-stu-id="25121-182">Allowed values</span></span>
    - <span data-ttu-id="25121-183">0: spegne il timer</span><span class="sxs-lookup"><span data-stu-id="25121-183">0 - turns off the timer</span></span>
    - <span data-ttu-id="25121-184">1: 1440 minuti per il ripristino del timer di inattività</span><span class="sxs-lookup"><span data-stu-id="25121-184">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="25121-185">Criteri di supporto per la modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="25121-185">Support policies for kiosk mode</span></span>

<span data-ttu-id="25121-186">Usa uno dei criteri di Microsoft Edge elencati nella tabella di seguito per ottimizzare l'esperienza del chiosco multimediale per il tipo di modalità tutto schermo di Microsoft Edge configurata.</span><span class="sxs-lookup"><span data-stu-id="25121-186">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="25121-187">Per ulteriori informazioni su questi criteri, vedi [Microsoft Edge - Informazioni di riferimento sui criteri del browser](https://docs.microsoft.com/deployedge/microsoft-edge-policies).</span><span class="sxs-lookup"><span data-stu-id="25121-187">To learn more about these policies, see [Microsoft Edge – Browser policy reference](https://docs.microsoft.com/deployedge/microsoft-edge-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="25121-188">La configurazione dei criteri non è limitata ai criteri elencati nella tabella di seguito, tuttavia i criteri aggiuntivi devono essere testati per verificare che la funzionalità della modalità tutto schermo non sia influenzata negativamente.</span><span class="sxs-lookup"><span data-stu-id="25121-188">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="25121-189">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="25121-189">Group policy</span></span>|<span data-ttu-id="25121-190">Segnaletica digitale/interattiva</span><span class="sxs-lookup"><span data-stu-id="25121-190">Digital\Interactive signage</span></span>|<span data-ttu-id="25121-191">App singola di esplorazione pubblica</span><span class="sxs-lookup"><span data-stu-id="25121-191">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="25121-192">Stampa</span><span class="sxs-lookup"><span data-stu-id="25121-192">Printing</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | <span data-ttu-id="25121-193">S</span><span class="sxs-lookup"><span data-stu-id="25121-193">Y</span></span>|<span data-ttu-id="25121-194">S</span><span class="sxs-lookup"><span data-stu-id="25121-194">Y</span></span> |
|[<span data-ttu-id="25121-195">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="25121-195">HomePageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |<span data-ttu-id="25121-196">N</span><span class="sxs-lookup"><span data-stu-id="25121-196">N</span></span> | <span data-ttu-id="25121-197">S</span><span class="sxs-lookup"><span data-stu-id="25121-197">Y</span></span>|
|[<span data-ttu-id="25121-198">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="25121-198">ShowHomeButton</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |<span data-ttu-id="25121-199">N</span><span class="sxs-lookup"><span data-stu-id="25121-199">N</span></span> | <span data-ttu-id="25121-200">S</span><span class="sxs-lookup"><span data-stu-id="25121-200">Y</span></span>|
|[<span data-ttu-id="25121-201">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="25121-201">NewTabPageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |<span data-ttu-id="25121-202">N</span><span class="sxs-lookup"><span data-stu-id="25121-202">N</span></span> |<span data-ttu-id="25121-203">S</span><span class="sxs-lookup"><span data-stu-id="25121-203">Y</span></span> |
|[<span data-ttu-id="25121-204">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="25121-204">FavoritesBarEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |<span data-ttu-id="25121-205">N</span><span class="sxs-lookup"><span data-stu-id="25121-205">N</span></span> |<span data-ttu-id="25121-206">S</span><span class="sxs-lookup"><span data-stu-id="25121-206">Y</span></span> |
|[<span data-ttu-id="25121-207">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="25121-207">URLAllowlist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |<span data-ttu-id="25121-208">S</span><span class="sxs-lookup"><span data-stu-id="25121-208">Y</span></span> |<span data-ttu-id="25121-209">S</span><span class="sxs-lookup"><span data-stu-id="25121-209">Y</span></span> |
|[<span data-ttu-id="25121-210">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="25121-210">URLBlocklist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |<span data-ttu-id="25121-211">S</span><span class="sxs-lookup"><span data-stu-id="25121-211">Y</span></span> | <span data-ttu-id="25121-212">S</span><span class="sxs-lookup"><span data-stu-id="25121-212">Y</span></span>|
|[<span data-ttu-id="25121-213">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="25121-213">ManagedSearchEngines</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |<span data-ttu-id="25121-214">N</span><span class="sxs-lookup"><span data-stu-id="25121-214">N</span></span> | <span data-ttu-id="25121-215">S</span><span class="sxs-lookup"><span data-stu-id="25121-215">Y</span></span>|
|[<span data-ttu-id="25121-216">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="25121-216">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |<span data-ttu-id="25121-217">N</span><span class="sxs-lookup"><span data-stu-id="25121-217">N</span></span> | <span data-ttu-id="25121-218">S</span><span class="sxs-lookup"><span data-stu-id="25121-218">Y</span></span>|
|[<span data-ttu-id="25121-219">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="25121-219">VerticalTabsAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | <span data-ttu-id="25121-220">N</span><span class="sxs-lookup"><span data-stu-id="25121-220">N</span></span>|<span data-ttu-id="25121-221">S</span><span class="sxs-lookup"><span data-stu-id="25121-221">Y</span></span> |
|[<span data-ttu-id="25121-222">Impostazioni SmartScreen</span><span class="sxs-lookup"><span data-stu-id="25121-222">SmartScreen settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |<span data-ttu-id="25121-223">S</span><span class="sxs-lookup"><span data-stu-id="25121-223">Y</span></span> |<span data-ttu-id="25121-224">S</span><span class="sxs-lookup"><span data-stu-id="25121-224">Y</span></span> |

## <span data-ttu-id="25121-225">Microsoft Edge con accesso assegnato</span><span class="sxs-lookup"><span data-stu-id="25121-225">Microsoft Edge with assigned access</span></span>

### <span data-ttu-id="25121-226">Chiosco multimediale con app singola</span><span class="sxs-lookup"><span data-stu-id="25121-226">Single app kiosk</span></span>

<span data-ttu-id="25121-227">Attualmente, Microsoft Edge supporta un sottogruppo delle stesse modalità tutto schermo della Versione legacy di Microsoft Edge per accesso assegnato con app singola con le seguenti esperienze di blocco: segnaletica digitale/interattiva ed esplorazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="25121-227">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="25121-228">La modalità tutto schermo con accesso assegnato è al momento disponibile per essere testata con l'ultima  [build di Windows 10 Insider Preview](https://insider.windows.com/), versione 20215 o successiva, e con il  [Canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), versione 87.0.644.4 o successiva.</span><span class="sxs-lookup"><span data-stu-id="25121-228">Kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4 or higher.</span></span>

**<span data-ttu-id="25121-229">Come ottengo l'anteprima di Windows Insiders?</span><span class="sxs-lookup"><span data-stu-id="25121-229">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="25121-230">Per installare una build di Windows 10 Insider Preview su PC, seguire le istruzioni in  [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).</span><span class="sxs-lookup"><span data-stu-id="25121-230">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="25121-231">Chiosco con più app</span><span class="sxs-lookup"><span data-stu-id="25121-231">Multi-app kiosk</span></span>

<span data-ttu-id="25121-232">Microsoft Edge può essere eseguito con [accesso assegnato con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) su Windows 10, che è l'equivalente del tipo di modalità tutto schermo per l'esplorazione normale di Microsoft Edge Legacy.</span><span class="sxs-lookup"><span data-stu-id="25121-232">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="25121-233">Per configurare Microsoft Edge con l'accesso assegnato con più app, segui le istruzioni su come [Configurare un chiosco multimediale con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span><span class="sxs-lookup"><span data-stu-id="25121-233">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="25121-234">(L'AUMID per il canale stabile Microsoft Edge è **MSEdge**.)</span><span class="sxs-lookup"><span data-stu-id="25121-234">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="25121-235">Quando usi Microsoft Edge con accesso assegnato con più app, puoi configurare il chiosco multimediale di Microsoft Edge in modo da utilizzare i [criteri del browser Microsoft Edge](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) per configurare l'esperienza di esplorazione per soddisfare i tuoi requisiti univoci.</span><span class="sxs-lookup"><span data-stu-id="25121-235">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <span data-ttu-id="25121-236">Configurare usando le impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="25121-236">Configure using Windows Settings</span></span>

<span data-ttu-id="25121-237">Il modo più semplice per configurare uno o due dispositivi in modalità tutto schermo con app singola è tramite le impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="25121-237">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="25121-238">Usa i seguenti passaggi per configurare un computer in modalità tutto schermo con app singola.</span><span class="sxs-lookup"><span data-stu-id="25121-238">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="25121-239">Installa l'ultima versione di Windows 10 Insider Preview, versione 20215 o successiva.</span><span class="sxs-lookup"><span data-stu-id="25121-239">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="25121-240">Segui le istruzioni in [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).</span><span class="sxs-lookup"><span data-stu-id="25121-240">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="25121-241">Installa l’ultima versione del [canale stabile Microsoft Edge](https://www.microsoft.com/edge), versione 87 o successiva.</span><span class="sxs-lookup"><span data-stu-id="25121-241">Install the latest version of [Microsoft Edge Stable channel](https://www.microsoft.com/edge), version 87 or higher.</span></span>  <span data-ttu-id="25121-242">Per testare le caratteristiche più recenti, puoi scaricare l’ultima versione del [canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), versione 89 o successiva.</span><span class="sxs-lookup"><span data-stu-id="25121-242">To test the latest features, you can download the latest [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="25121-243">Poiché è richiesta un'installazione a livello di dispositivo, è supportato solo un canale non Canary.</span><span class="sxs-lookup"><span data-stu-id="25121-243">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="25121-244">Dal computer di un chiosco multimediale, apri le Impostazioni di Windows e digita "chiosco" nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="25121-244">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="25121-245">Seleziona  **Configura un chiosco multimediale (accesso assegnato**), mostrato nella schermata successiva per aprire la finestra di dialogo per la creazione del chiosco.</span><span class="sxs-lookup"><span data-stu-id="25121-245">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

4. <span data-ttu-id="25121-247">Nella pagina **Configura un chiosco multimediale** , fai clic su  **Inizia**.</span><span class="sxs-lookup"><span data-stu-id="25121-247">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="Pagina chiosco multimediale: Introduzione":::

5. <span data-ttu-id="25121-249">Digita un nome per creare un nuovo account per chiosco multimediale o scegli un account esistente dall'elenco a discesa popolato e quindi fai clic su  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="25121-249">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="Modalità tutto schermo: crea un account":::

6. <span data-ttu-id="25121-251">Nella pagina **Scegli un'app chiosco multimediale** , seleziona **Microsoft Edge** e quindi fai clic su  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="25121-251">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="25121-252">Questo si applica solo ai canali Microsoft Edge Dev, Beta e Stable.</span><span class="sxs-lookup"><span data-stu-id="25121-252">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="Modalità tutto schermo: scegli un’app":::

7. <span data-ttu-id="25121-254">Scegli una delle seguenti opzioni per la modalità di visualizzazione di Microsoft Edge durante l'esecuzione in modalità tutto schermo:</span><span class="sxs-lookup"><span data-stu-id="25121-254">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="25121-255">Segnaletica digitale/interattiva - Visualizza un sito specifico in modalità a schermo intero, con Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="25121-255">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="25121-256">Browser pubblico - Esegue una versione multi-scheda limitata di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="25121-256">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="Visualizzazione in modalità tutto schermo: segno digitale in modalità a schermo intero":::

8. <span data-ttu-id="25121-258">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="25121-258">Select **Next**.</span></span>
9. <span data-ttu-id="25121-259">Digita l'URL da caricare all'avvio del chiosco.</span><span class="sxs-lookup"><span data-stu-id="25121-259">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="Modalità tutto schermo: immetti l'URL":::

10. <span data-ttu-id="25121-261">Accetta il valore predefinito di 5 minuti per il tempo di inattività o fornisci un valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="25121-261">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="Modalità tutto schermo: immettere il tempo di inattività":::

11. <span data-ttu-id="25121-263">Fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="25121-263">Click **Next**.</span></span>
12. <span data-ttu-id="25121-264">Chiudi la finestra **Impostazioni**  per salvare e applicare le tue scelte.</span><span class="sxs-lookup"><span data-stu-id="25121-264">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="Modalità tutto schermo: completare la configurazione":::

13. <span data-ttu-id="25121-266">Disconnettiti dal chiosco multimediale ed esegui l'accesso con l'account chiosco locale per convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="25121-266">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="25121-267">Limitazioni funzionali</span><span class="sxs-lookup"><span data-stu-id="25121-267">Functional limitations</span></span>

<span data-ttu-id="25121-268">Con il rilascio della versione di anteprima della modalità tutto schermo stiamo continuando a migliorare il prodotto e aggiungere nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="25121-268">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="25121-269">È consigliabile disattivare:</span><span class="sxs-lookup"><span data-stu-id="25121-269">We recommend that you turn off:</span></span>

- [<span data-ttu-id="25121-270">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="25121-270">StartupBoostEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [<span data-ttu-id="25121-271">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="25121-271">InternetExplorerIntegrationLevel</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [<span data-ttu-id="25121-272">Extensions</span><span class="sxs-lookup"><span data-stu-id="25121-272">Extensions</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [<span data-ttu-id="25121-273">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="25121-273">BackgroundModeEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## <span data-ttu-id="25121-274">Roadmap</span><span class="sxs-lookup"><span data-stu-id="25121-274">Roadmap</span></span>

### <span data-ttu-id="25121-275">All'inizio del 2021</span><span class="sxs-lookup"><span data-stu-id="25121-275">In early 2021</span></span>

<span data-ttu-id="25121-276">Verranno aggiunte le funzionalità e il supporto seguenti:</span><span class="sxs-lookup"><span data-stu-id="25121-276">We'll add the following support and features:</span></span>

- <span data-ttu-id="25121-277">Disponibilità generale della modalità tutto schermo di Microsoft Edge con accesso assegnato con app singola su Windows 10 1909 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="25121-277">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="25121-278">Funzionalità aggiuntive per la parità con la Versione legacy di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="25121-278">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="25121-279">Integrazione con Intune per configurare i dispositivi con l’esperienza utente del profilo in modalità tutto schermo.</span><span class="sxs-lookup"><span data-stu-id="25121-279">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="25121-280">I tasti di scelta rapida aggiuntivi verranno bloccati.</span><span class="sxs-lookup"><span data-stu-id="25121-280">Additional keyboard shortcuts will be blocked.</span></span>
- <span data-ttu-id="25121-281">Limitazione del lancio di altre applicazioni dal browser.</span><span class="sxs-lookup"><span data-stu-id="25121-281">Restrict the launch of other applications from the browser.</span></span>

## <span data-ttu-id="25121-282">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="25121-282">See also</span></span>

- [<span data-ttu-id="25121-283">Configurare chioschi multimediali e firme digitali nelle edizioni desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="25121-283">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="25121-284">Distribuire la modalità tutto schermo di Microsoft Edge Legacy</span><span class="sxs-lookup"><span data-stu-id="25121-284">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="25121-285">Pianificare la distribuzione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="25121-285">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="25121-286">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="25121-286">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
