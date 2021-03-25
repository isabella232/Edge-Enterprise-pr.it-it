---
title: Compatibilità con le versioni precedenti per la nuova pagina della scheda Enterprise
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 10/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Compatibilità con le versioni precedenti per la nuova pagina della scheda Enterprise
ms.openlocfilehash: 5721db16c634250b3a586f6bd1b6b531a07815a5
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447260"
---
# <a name="backwards-compatibility-for-the-enterprise-new-tab-page"></a><span data-ttu-id="c6c72-103">Compatibilità con le versioni precedenti per la nuova pagina della scheda Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6c72-103">Backwards compatibility for the Enterprise New tab page</span></span>

<span data-ttu-id="c6c72-104">Questo articolo descrive la variazione della nuova pagina della scheda e il modo in cui gli utenti possono garantire la compatibilità con Microsoft Edge versione 87 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="c6c72-104">This article describes the change to the New tab page and how users can be backwards compatible with Microsoft Edge version 87 and earlier.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c72-105">Questo articolo si applica a Microsoft Edge versione 87 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c6c72-105">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="information-feeds-from-single-endpoint"></a><span data-ttu-id="c6c72-106">Feed informazioni da un unico endpoint</span><span class="sxs-lookup"><span data-stu-id="c6c72-106">Information feeds from single endpoint</span></span>

<span data-ttu-id="c6c72-107">La nuova versione della pagina della scheda Enterprise coniuga i contenuti conformi a Microsoft 365 e i feed informazione pertinenti e conformi al settore, che vengono serviti tramite l'endpoint MSN.com.</span><span class="sxs-lookup"><span data-stu-id="c6c72-107">The new version of the Enterprise New tab page combines compliant Microsoft 365 content with industry relevant and compliant information feeds that are served via the MSN.com endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c72-108">I contenuti di Office 365 sono stati in origine serviti usando il dominio[](https://www.office.com)Office.com[.](https://www.office.com)</span><span class="sxs-lookup"><span data-stu-id="c6c72-108">Office 365 content was originally served using the [Office.com](https://www.office.com) domain.</span></span>

<span data-ttu-id="c6c72-109">Se l'accesso al dominio MSN.com è limitato alla propria organizzazione, è consigliabile offrire agli utenti l'accesso a questo [URL](https://ntp.msn.com).</span><span class="sxs-lookup"><span data-stu-id="c6c72-109">If access to the MSN.com domain is restricted for your organization, we strongly recommend giving users access to this [url](https://ntp.msn.com).</span></span>

<span data-ttu-id="c6c72-110">Qualora fosse necessario più tempo per abilitare l'accesso al dominio MSN, si consiglia di usare [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype), che consente di scegliere l'esperienza feed di Microsoft News oppure Office 365 per la nuova pagina della scheda.</span><span class="sxs-lookup"><span data-stu-id="c6c72-110">If you need more time to enable access to the MSN domain, we recommend using the [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype), that lets you choose either the Microsoft News or Office 365 feed experience for the new tab page.</span></span>

### <a name="keep-using-officecom"></a><span data-ttu-id="c6c72-111">Continuare a usare Office.com</span><span class="sxs-lookup"><span data-stu-id="c6c72-111">Keep using Office.com</span></span>

 <span data-ttu-id="c6c72-112">È possibile configurare il criterio **NewTabPageSetFeedType** per continuare a usare il dominio deprecato Office.com.</span><span class="sxs-lookup"><span data-stu-id="c6c72-112">You can configure the **NewTabPageSetFeedType** policy to keep using the deprecated Office.com domain.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6c72-113">Il criterio **NewTabPageSetFeedType** e il dominio Office.com che serve i contenuti Office 365 smetterà di funzionare una volta rilasciata la versione 90 di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="c6c72-113">The **NewTabPageSetFeedType** policy and the Office.com domain that serves Office 365 content will quit working when Microsoft Edge version 90 is released.</span></span>

<span data-ttu-id="c6c72-114">Le seguenti impostazioni del criterio faranno in modo che la nuova pagina della scheda Enterprise esegua il rendering dei contenuti dei documenti di Office dal dominio Office.com.</span><span class="sxs-lookup"><span data-stu-id="c6c72-114">The following policy settings will force the Enterprise New tab page to render Office document content from the Office.com domain.</span></span>

- <span data-ttu-id="c6c72-115">Impostare il criterio come **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="c6c72-115">Set the policy as **Mandatory**.</span></span>
- <span data-ttu-id="c6c72-116">Impostare il valore del mapping del criterio su **Office (1) = esperienza feed di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="c6c72-116">Set the value of the policy mapping to **Office (1) = Office 365 feed experience**.</span></span>

<span data-ttu-id="c6c72-117">Qualora non fosse possibile passare a Office.com, inviare il proprio feedback.</span><span class="sxs-lookup"><span data-stu-id="c6c72-117">If the switch to the Office.com isn't possible, reach out and send us feedback.</span></span> <span data-ttu-id="c6c72-118">Un'altra opzione consiste nel configurare [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) in modo che punti a un URL di endpoint consentito dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6c72-118">Another option is to configure the [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) so it points to an endpoint URL that's allowed by your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c72-119">Il criterio **NewTabPageLocation** ha precedenza se il criterio **NewTabPageSetFeedType** è configurato.</span><span class="sxs-lookup"><span data-stu-id="c6c72-119">The **NewTabPageLocation** policy has precedence if the **NewTabPageSetFeedType** policy is also configured.</span></span>

## <a name="enterprise-users-will-now-get-microsoft-news-content-via-my-feed"></a><span data-ttu-id="c6c72-120">Ora gli utenti Enterprise otterranno i contenuti di Microsoft News Feed personale.</span><span class="sxs-lookup"><span data-stu-id="c6c72-120">Enterprise users will now get Microsoft news content via My Feed</span></span>

<span data-ttu-id="c6c72-121">La nuova pagina della scheda Enterprise offrirà informazioni rilevanti di settore in **Feed personale** e il contenuto di Office 365 in una singola visualizzazione per gli utenti che hanno eseguito l'accesso con l'account di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c6c72-121">The Enterprise New tab page will offer industry relevant information in **My Feed** and Office 365 content in a single view for users signed in with their Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="c6c72-122">Per gli utenti che hanno eseguito l'accesso all'account Azure Active Directory (Azure AD) e che hanno selezionato l'opzione Microsoft News nel riquadro a comparsa Impostazioni, la visualizzazione della nuova pagina della scheda verrà sostituita dal contenuto **Feed personale**.</span><span class="sxs-lookup"><span data-stu-id="c6c72-122">For users signed in with their Azure Active Directory (Azure AD) who selected the Microsoft News option in the settings flyout, their new tab page view will be replaced with **My Feed** content.</span></span> <span data-ttu-id="c6c72-123">Quando verrà aperta una nuova scheda nel browser, l'aspetto sarà simile all'esempio indicato nello screenshot seguente.</span><span class="sxs-lookup"><span data-stu-id="c6c72-123">When they open a new tab page in the browser it will look like the example in the next screenshot.</span></span>

![Nuova pagina della scheda che mostra il contenuto del Feed personale.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> <span data-ttu-id="c6c72-125">Gli utenti che non hanno eseguito l'accesso con Azure AD continueranno a visualizzare il feed MSN News quando viene aperta una nuova scheda.</span><span class="sxs-lookup"><span data-stu-id="c6c72-125">Users who aren't signed in with Azure AD will continue to see the MSN News feed when they open a new tab.</span></span>

## <a name="page-layout"></a><span data-ttu-id="c6c72-126">Layout di pagina</span><span class="sxs-lookup"><span data-stu-id="c6c72-126">Page layout</span></span>

<span data-ttu-id="c6c72-127">Grazie alle modifiche apportate alla nuova pagina della scheda, il layout di pagina non dovrà più controllare due tipi di contenuto specifici (Office 365 e Microsoft News), in modo che l'interruttore attiva/disattiva contenuto non sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="c6c72-127">With the changes to the New tab page, the Page layout no longer has to control two specific content types (Office 365 and Microsoft News), so the content toggle isn't available.</span></span> <span data-ttu-id="c6c72-128">Lo screenshot seguente mostra il riquadro a comparsa per il layout di pagina.</span><span class="sxs-lookup"><span data-stu-id="c6c72-128">The next screenshot shows the flyout for the Page layout.</span></span>

![Visualizzazione layout di pagina per la nuova pagina della scheda.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

<span data-ttu-id="c6c72-130">Se si desidera continuare ad accedere ai contenuti di Microsoft News non collegati all'organizzazione, è necessario usare un profilo browser diverso.</span><span class="sxs-lookup"><span data-stu-id="c6c72-130">If you want to keep accessing Microsoft News content that isn't tied to your organization, you must use a different browser profile.</span></span> <span data-ttu-id="c6c72-131">Passare a *edge://settings/profiles* e disconnettersi dal profilo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6c72-131">Go to  *edge://settings/profiles* and sign out of your Azure AD profile.</span></span> <span data-ttu-id="c6c72-132">Questa azione fornisce una visualizzazione standard della nuova scheda Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c6c72-132">This action will bring up the  standard view for the Enterprise new tab page.</span></span> 

## <a name="see-also"></a><span data-ttu-id="c6c72-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6c72-133">See also</span></span>

- [<span data-ttu-id="c6c72-134">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6c72-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c6c72-135">Modalità Enterprise per Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="c6c72-135">Enterprise Mode for Internet Explorer 11</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)