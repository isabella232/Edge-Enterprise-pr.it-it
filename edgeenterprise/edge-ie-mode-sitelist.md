---
title: Strategia di configurazione sito Enterprise
ms.author: shisub
author: shisub
manager: srugh
ms.date: 05/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Una guida dettagliata alla configurazione dell'elenco dei siti modalità Enterprise per la modalità Internet Explorer.
ms.openlocfilehash: 7369e4e14f33fc37c6ded0ebc7df57d64a34df50
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617396"
---
# <a name="enterprise-site-configuration-strategy"></a><span data-ttu-id="d3bc2-103">Strategia di configurazione sito Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3bc2-103">Enterprise site configuration strategy</span></span>

>[!Note]
> <span data-ttu-id="d3bc2-104">L'applicazione desktop di Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto il 15 giugno 2022 (per un elenco degli elementi interessati, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span><span class="sxs-lookup"><span data-stu-id="d3bc2-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="d3bc2-105">Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti Microsoft Edge in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="d3bc2-106">[Altre informazioni qui](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span><span class="sxs-lookup"><span data-stu-id="d3bc2-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="d3bc2-107">Questo articolo descrive le modifiche apportate all'elenco dei siti in modalità Enterprise per supportare la modalità Internet Explorer per Microsoft Edge, versione 77 e successive.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-107">This article describes changes to the Enterprise Mode Site List to support Internet Explorer mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="d3bc2-108">Per altre informazioni sullo schema per il file XML dell'elenco di siti in modalità Enterprise, vedere [Indicazioni per lo schema v.2 della modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span><span class="sxs-lookup"><span data-stu-id="d3bc2-108">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="d3bc2-109">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-109">This article applies to Microsoft Edge version 77 or later.</span></span>
<!--
## Updated schema elements

The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:

| **Element** | **Description** |
| --- | --- |
| \<open-in app="**true**"\> | A child element that controls what browser is used for sites. This element is required for sites that need to **open in IE11**.|

**Example:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

The following table shows the possible values of the \<open-in\> element:

| **Value** | **Description** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Opens the site in IE mode or a full IE11 window. To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Opens the site in a full IE11 window |
| **\<open-in\>MSEdge\</open-in\>** | Opens the site in Microsoft Edge |
| **\<open-in\>None or not specified\</open-in\>** | Opens the site in the default browser or in the browser where the user navigated to the site. |
|**\<open-in\>Configurable\</open-in\>** | Allows the site to participate in IE mode engine determination. To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_. Adding it to the other 'open-in' elements won't change browser behavior.   -->

## <a name="configuration-strategy"></a><span data-ttu-id="d3bc2-110">Strategia di configurazione</span><span class="sxs-lookup"><span data-stu-id="d3bc2-110">Configuration strategy</span></span>

<span data-ttu-id="d3bc2-111">I passaggi seguenti fanno parte di una strategia di configurazione del sito per la modalità IE:</span><span class="sxs-lookup"><span data-stu-id="d3bc2-111">The following steps are part of a site configuration strategy for IE mode:</span></span>
1. <span data-ttu-id="d3bc2-112">Preparare l'elenco dei siti</span><span class="sxs-lookup"><span data-stu-id="d3bc2-112">Prepare your site list</span></span>
2. <span data-ttu-id="d3bc2-113">Configurare i siti neutri</span><span class="sxs-lookup"><span data-stu-id="d3bc2-113">Configure neutral sites</span></span>
3. <span data-ttu-id="d3bc2-114">(Facoltativo) Utilizzare la condivisione dei cookie, se necessario</span><span class="sxs-lookup"><span data-stu-id="d3bc2-114">(Optional) Use cookie sharing if necessary</span></span>

<!--
Step 1.  – if you don’t have one use Site Discovery Step-by-Step
Step 2 – Neutral sites + sticky mode
        Use more examples and explain sticky mode better
Step 3 – If that doesn’t cover your needs, then use Cookie sharing -->

## <a name="prepare-your-site-list"></a><span data-ttu-id="d3bc2-115">Preparare l'elenco dei siti</span><span class="sxs-lookup"><span data-stu-id="d3bc2-115">Prepare your site list</span></span>

<span data-ttu-id="d3bc2-116">Se si dispone già di un elenco di siti in modalità Enterprise per IE11 o Microsoft Edge Legacy, è possibile riutilizzarlo per configurare la modalità IE.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-116">If you already have an Enterprise Mode site list for IE11 or Microsoft Edge Legacy, you can reuse it to configure IE mode.</span></span>

<span data-ttu-id="d3bc2-117">Tuttavia, se non si dispone di un elenco di siti, è possibile utilizzare lo strumento [Enterprise Site Discovery tool](/deployedge/edge-ie-mode-site-discovery) per popolare l'elenco dei siti.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-117">However, if you don't have a site list, you can use the [Enterprise Site Discovery tool](/deployedge/edge-ie-mode-site-discovery) to populate your site list.</span></span>

## <a name="configure-neutral-sites"></a><span data-ttu-id="d3bc2-118">Configurare i siti neutri</span><span class="sxs-lookup"><span data-stu-id="d3bc2-118">Configure neutral sites</span></span>

<span data-ttu-id="d3bc2-119">Per il corretto funzionamento della modalità IE, i server SSO (Single Sign-On) di autenticazione e autenticazione dovranno essere configurati in modo esplicito come siti neutri.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-119">In order for IE mode to work properly, authentication / Single Sign-On (SSO) servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="d3bc2-120">In caso contrario, le pagine in modalità IE tenteranno di reindirizzare a Microsoft Edge e l'autenticazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-120">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="d3bc2-121">Quando viene avviata la navigazione, un sito neutrale usa il browser Microsoft Edge o la modalità IE.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-121">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="d3bc2-122">La configurazione dei siti neutri garantisce che le applicazioni che usano tali server di autenticazione, moderni e legacy, continuino a funzionare.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-122">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="d3bc2-123">È possibile configurare i siti neutri impostando l'elenco a discesa *Apri in* su 'Nessuno' nello strumento Enterprise Mode Site List Manager o aggiornando direttamente il file XML dell'elenco siti:</span><span class="sxs-lookup"><span data-stu-id="d3bc2-123">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="d3bc2-124">Per identificare i server di autenticazione, analizzare il traffico di rete da un'applicazione che usa gli strumenti di sviluppo di IE11.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-124">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="d3bc2-125">Se serve più tempo per identificare i server di autenticazione, è possibile configurare un criterio in modo che tutti gli spostamenti nella pagina rimangano in modalità IE per consentire agli utenti di proseguire i loro flussi di lavoro senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-125">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigations in IE mode to allow your users to continue their workflows uninterrupted.</span></span> <span data-ttu-id="d3bc2-126">Per ridurre al minimo l'uso della modalità IE quando non è necessario, disabilitare questa impostazione dopo aver identificato e aggiunto i server di autenticazione all'elenco dei siti.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-126">To minimize the use of IE mode when unnecessary, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="d3bc2-127">Per ulteriori informazioni, vedere [Mantenere lo spostamento nella pagina in modalità IE](/deployedge/edge-learnmore-inpage-nav).</span><span class="sxs-lookup"><span data-stu-id="d3bc2-127">For more information, see [Keep in-page navigation in IE mode](/deployedge/edge-learnmore-inpage-nav).</span></span>

>[!NOTE]
   ><span data-ttu-id="d3bc2-128">Lo schema per la modalità Enterprise v.1 non è supportato per l'integrazione della modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-128">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="d3bc2-129">Se attualmente usi lo schema v.1 con Internet Explorer 11, devi eseguire l'aggiornamento allo schema v.2.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-129">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="d3bc2-130">Per altre informazioni, vedere [Indicazioni per lo schema v.2 della modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span><span class="sxs-lookup"><span data-stu-id="d3bc2-130">For more information, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <a name="optional-use-cookie-sharing-if-necessary"></a><span data-ttu-id="d3bc2-131">(Facoltativo) Utilizzare la condivisione dei cookie, se necessario</span><span class="sxs-lookup"><span data-stu-id="d3bc2-131">(Optional) Use cookie sharing if necessary</span></span>

<span data-ttu-id="d3bc2-132">Per impostazione predefinita, i processi di Microsoft Edge e Internet Explorer non condividono i cookie di sessione e questa mancanza di condivisione può essere scomoda in alcuni casi durante l'uso della modalità IE.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-132">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this lack of sharing can be inconvenient in some cases while using IE mode.</span></span> <span data-ttu-id="d3bc2-133">Ad esempio, quando un utente deve eseguire di nuovo l'autenticazione in modalità IE se in precedenza è abituato a farlo o quando si disconnette da una sessione di Microsoft Edge non si disconnette dalla sessione in modalità Internet Explorer per le transazioni critiche.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-133">For example, when a user has to reauthenticate in IE mode when previously they are accustomed to doing so or when signing out of a Microsoft Edge session doesn’t sign out of the Internet Explorer mode session for critical transactions.</span></span> <span data-ttu-id="d3bc2-134">In questi scenari, è possibile configurare cookie specifici impostati da SSO per l'invio da Microsoft Edge a Internet Explorer in modo che l'esperienza di autenticazione diventi più semplice eliminando la necessità di eseguire di nuovo l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d3bc2-134">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to reauthenticate.</span></span> <span data-ttu-id="d3bc2-135">Per altre informazioni, vedere [Condivisione cookie da Microsoft Edge a Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare).</span><span class="sxs-lookup"><span data-stu-id="d3bc2-135">For more information, see [Cookie sharing from Microsoft Edge to Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3bc2-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3bc2-136">See also</span></span>

- [<span data-ttu-id="d3bc2-137">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3bc2-137">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="d3bc2-138">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="d3bc2-138">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="d3bc2-139">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3bc2-139">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
