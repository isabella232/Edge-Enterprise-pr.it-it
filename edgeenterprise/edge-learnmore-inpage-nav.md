---
title: Mantenere lo spostamento nella pagina in modalità Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Mantenere lo spostamento nella pagina in modalità Internet Explorer
ms.openlocfilehash: 0acca9e05a0d09b02fa61d5ddd7de3f7c6cabb92
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980222"
---
# <span data-ttu-id="82814-103">Mantenere lo spostamento nella pagina in modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="82814-103">Keep in-page navigation in Internet Explorer mode</span></span>

<span data-ttu-id="82814-104">È possibile usare questo criterio come soluzione temporanea per forzare lo spostamento nella pagina dei siti in modalità Internet Explorer (modalità IE) a rimanere in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="82814-104">You can use this policy as a temporary solution to force all in-page navigation from Internet Explorer mode (IE mode) sites to stay in IE mode.</span></span>

<span data-ttu-id="82814-105">Lo spostamento nella pagina viene avviato da un collegamento, uno script o una maschera nella pagina corrente.</span><span class="sxs-lookup"><span data-stu-id="82814-105">An in-page navigation is started from a link, a script, or a form on the current page.</span></span> <span data-ttu-id="82814-106">Può essere anche avviato da un reindirizzamento lato server di un precedente tentativo di spostamento nella pagina.</span><span class="sxs-lookup"><span data-stu-id="82814-106">It can also be a server-side redirect of a previous in-page navigation attempt.</span></span> <span data-ttu-id="82814-107">Al contrario un utente può avviare uno spostamento che non sia nella pagina, e indipendentemente dalla pagina corrente, in diversi modi usando i controlli del browser.</span><span class="sxs-lookup"><span data-stu-id="82814-107">Conversely, a user can start a navigation that isn't in-page that's independent of the current page in several ways by using the browser controls.</span></span> <span data-ttu-id="82814-108">Ad esempio, usando la barra degli indirizzi, il pulsante indietro o un collegamento preferito.</span><span class="sxs-lookup"><span data-stu-id="82814-108">For example, using the address bar, the back button, or a favorite link.</span></span>

>[!NOTE]
><span data-ttu-id="82814-109">Questo articolo si applica a Microsoft Edge, versione 81 o successiva.</span><span class="sxs-lookup"><span data-stu-id="82814-109">This article applies to Microsoft Edge version 81 or later.</span></span>

## <span data-ttu-id="82814-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="82814-110">Prerequisites</span></span>

<span data-ttu-id="82814-111">Per questo criterio sono necessari gli aggiornamenti di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="82814-111">The following Windows updates are required for this policy:</span></span>

- <span data-ttu-id="82814-112">Windows 10, versioni 1909 e 1903; Windows Server, versioni 1909 e 1903  ([KB4532695](https://support.microsoft.com/help/4532695))</span><span class="sxs-lookup"><span data-stu-id="82814-112">Windows 10 version 1909 & 1903, Windows Server version 1909 & 1903  ([KB4532695](https://support.microsoft.com/help/4532695))</span></span>
- <span data-ttu-id="82814-113">Windows 10, versione 1809; Windows Server, versione 1809, e Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span><span class="sxs-lookup"><span data-stu-id="82814-113">Windows 10 version 1809, Windows Server version 1809, Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span></span>
- <span data-ttu-id="82814-114">Windows 10, versione 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span><span class="sxs-lookup"><span data-stu-id="82814-114">Windows 10 version 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span></span>
- <span data-ttu-id="82814-115">Windows 10, versione 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span><span class="sxs-lookup"><span data-stu-id="82814-115">Windows 10 version 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span></span>


## <span data-ttu-id="82814-116">Informazioni sul criterio</span><span class="sxs-lookup"><span data-stu-id="82814-116">About this policy</span></span>

<span data-ttu-id="82814-117">Questo criterio consente di identificare e configurare tutti i server di autenticazione usati dai propri siti in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="82814-117">This policy gives you time to identify and configure all of the authentication servers used by your IE mode sites.</span></span> <span data-ttu-id="82814-118">Tuttavia, il criterio può comportare un'esperienza di navigazione incoerente poiché alcuni siti effettuano il rendering in modalità Internet Explorer e altre volte in modalità Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="82814-118">However, this policy can result in an inconsistent browsing experience, where some sites are rendered in IE mode and at other times rendered in Microsoft Edge mode.</span></span> <span data-ttu-id="82814-119">Questa esperienza varia a seconda che lo spostamento al sito abbia avuto inizio da una pagina in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="82814-119">This experience depends on whether the navigation to the site began from an IE mode page.</span></span> <span data-ttu-id="82814-120">I siti non configurati in modo esplicito per l'apertura in un motore di rendering specifico sono soggetti a questa incoerenza.</span><span class="sxs-lookup"><span data-stu-id="82814-120">Any site that isn't explicitly configured to open in a specific rendering engine will be subject to this inconsistency.</span></span>

<span data-ttu-id="82814-121">Se si abilita questo criterio, è consigliabile disabilitarlo dopo aver identificato tutti i server di autenticazione e averli aggiunti all'elenco del sito come server neutri.</span><span class="sxs-lookup"><span data-stu-id="82814-121">If you enable this policy, we recommend that you disable it after you've identified all the authentication servers and added them to the site list as neutral.</span></span> <span data-ttu-id="82814-122">In questo modo, i siti moderni non effettueranno mai inavvertitamente il rendering in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="82814-122">This action ensures that your modern sites never inadvertently render in IE mode.</span></span>

## <span data-ttu-id="82814-123">Mantenere lo spostamento nella pagina in modalità IE</span><span class="sxs-lookup"><span data-stu-id="82814-123">Keep in-page navigation in IE mode</span></span>

<span data-ttu-id="82814-124">Per mantenere lo spostamento automatico o tutto lo spostamento nella pagina in modalità Internet Explorer, seguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="82814-124">To keep automatic or all in-page navigation in Internet Explorer mode, follow these steps:</span></span>

1. <span data-ttu-id="82814-125">Aprire l'Editor Criteri di gruppo locali.</span><span class="sxs-lookup"><span data-stu-id="82814-125">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="82814-126">Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="82814-126">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="82814-127">In **impostazione** fare doppio clic su **Specificare il comportamento degli spostamenti "nella pagina" verso i siti non configurati all'avvio dalle pagine in modalità Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="82814-127">Under **Setting**, double-click **Specify how "in-page" navigations to unconfigured sites behave when started from Internet Explorer mode pages**.</span></span>

   ![Impostazione dei criteri nella pagina](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. <span data-ttu-id="82814-129">Seleziona **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="82814-129">Select **Enabled**</span></span> 

   ![Abilitazione dei criteri nella pagina](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. <span data-ttu-id="82814-131">Scegliere una delle seguenti opzioni dall'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="82814-131">Choose one of the following options from the dropdown list:</span></span>

   - <span data-ttu-id="82814-132">**Impostazione predefinita**: solo i siti configurati per l'apertura in modalità Internet Explorer verranno aperti in questa modalità.</span><span class="sxs-lookup"><span data-stu-id="82814-132">**Default** - Only sites configured to open in Internet Explorer mode will open in that mode.</span></span> <span data-ttu-id="82814-133">I siti non configurati per l'apertura in modalità Internet Explorer verranno reindirizzati a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="82814-133">Any site not configured to open in Internet Explorer mode will be redirected back to Microsoft Edge.</span></span>
   - <span data-ttu-id="82814-134">**Mantenere solo lo spostamento automatico in modalità Internet Explorer**: usare questa opzione se si vuole mantenere l'esperienza predefinita tranne gli spostamenti automatici (ad esempio 302 reindirizzamenti) ai siti non configurati in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="82814-134">**Keep only automatic navigations in Internet Explorer mode** - Use this option if you want the default experience except that all automatic navigations (such as 302 redirects) to unconfigured sites will be kept in Internet Explorer mode.</span></span>
   - <span data-ttu-id="82814-135">**Mantenere tutto lo spostamento nella pagina in modalità Internet Explorer** ***(meno consigliata)***: tutti gli spostamenti dalle pagine caricate in modalità IE verso siti non configurati vengono mantenuti in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="82814-135">**Keep all in-page navigation in Internet Explorer mode** ***(Least Recommended)*** - All navigations from pages loaded in IE mode to unconfigured sites are kept in Internet Explorer mode.</span></span>

6. <span data-ttu-id="82814-136">Fare clic su **OK** o su **Applica** per salvare queste impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="82814-136">Click **OK** or **Apply** to save the policy settings.</span></span>

## <span data-ttu-id="82814-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82814-137">See also</span></span>

- [<span data-ttu-id="82814-138">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="82814-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
