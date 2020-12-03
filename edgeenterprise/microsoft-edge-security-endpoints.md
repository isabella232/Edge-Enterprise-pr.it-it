---
title: Elenco Consenti per gli endpoint Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 11/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Elenco Consenti per gli endpoint Microsoft Edge
ms.openlocfilehash: 3d46e2e8c85eadc39cf9788df44b45592ea4fb1b
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194691"
---
# <span data-ttu-id="3d568-103">Elenco Consenti per gli endpoint Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d568-103">Allow list for Microsoft Edge endpoints</span></span>

<span data-ttu-id="3d568-104">Microsoft Edge richiede la connettività a Internet per supportare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3d568-104">Microsoft Edge requires connectivity to the Internet to support its features.</span></span> <span data-ttu-id="3d568-105">Questo articolo identifica gli URL di dominio che è necessario aggiungere all'elenco Consenti per garantire le comunicazioni tramite firewall e altri meccanismi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3d568-105">This article identifies the domain URLs that you need to add to the Allow list to ensure communications through firewalls and other security mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="3d568-106">Si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="3d568-106">This applies  to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="3d568-107">URL di dominio da consentire</span><span class="sxs-lookup"><span data-stu-id="3d568-107">Domain URLs to allow</span></span>

<span data-ttu-id="3d568-108">Consenti gli URL di dominio seguenti per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="3d568-108">Allow the following domain URLs for Microsoft Edge.</span></span>

### <span data-ttu-id="3d568-109">Servizio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="3d568-109">Update Service</span></span>

<span data-ttu-id="3d568-110">Il servizio che Microsoft Edge utilizza per verificare la disponibilità di nuovi aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="3d568-110">The service that Microsoft Edge uses to check for new updates.</span></span>

- `https://msedge.api.cdp.microsoft.com`

### <span data-ttu-id="3d568-111">Servizio di sperimentazione e configurazione</span><span class="sxs-lookup"><span data-stu-id="3d568-111">Experimentation and Configuration service</span></span>

- `https://config.edge.skype.com`

### <span data-ttu-id="3d568-112">Siti di download per Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d568-112">Download locations for Microsoft Edge</span></span>

<span data-ttu-id="3d568-113">Siti per il download di Microsoft Edge durante un'installazione iniziale o quando è disponibile un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3d568-113">Locations Microsoft Edge can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="3d568-114">Il sito di download è determinato dal servizio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3d568-114">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="3d568-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="3d568-115">HTTP</span></span>

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="3d568-116">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3d568-116">HTTPS</span></span>

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="3d568-117">Per semplificare l'elenco Consenti per i siti di download è possibile usare un carattere jolly:</span><span class="sxs-lookup"><span data-stu-id="3d568-117">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="3d568-118">Siti di download per le estensioni di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d568-118">Download locations for Microsoft Edge Extensions</span></span>

<span data-ttu-id="3d568-119">Siti per il download delle estensioni di Microsoft Edge durante un'installazione iniziale o quando è disponibile un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3d568-119">Locations Microsoft Edge Extensions can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="3d568-120">Il sito di download è determinato dal servizio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3d568-120">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="3d568-121">HTTP</span><span class="sxs-lookup"><span data-stu-id="3d568-121">HTTP</span></span>

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="3d568-122">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3d568-122">HTTPS</span></span>

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="3d568-123">Per semplificare l'elenco Consenti per i siti di download è possibile usare un carattere jolly:</span><span class="sxs-lookup"><span data-stu-id="3d568-123">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="3d568-124">Facoltativamente per il download dell'ottimizzazione recapito</span><span class="sxs-lookup"><span data-stu-id="3d568-124">Optionally for Download Delivery Optimization</span></span>

<span data-ttu-id="3d568-125">Per informazioni sull'ottimizzazione recapito, vedi [Ottimizzazione recapito per gli aggiornamenti di Windows 10](https://aka.ms/waas-do).</span><span class="sxs-lookup"><span data-stu-id="3d568-125">For information about delivery optimization, see [Delivery Optimization for Windows 10 updates](https://aka.ms/waas-do).</span></span>

- <span data-ttu-id="3d568-126">Comunicazioni da client a servizio: `*.do.dsp.mp.microsoft.com` (porta HTTP 80, porta HTTPS 443)</span><span class="sxs-lookup"><span data-stu-id="3d568-126">Client to Service communication: `*.do.dsp.mp.microsoft.com` (HTTP Port 80, HTTPS Port 443)</span></span>
- <span data-ttu-id="3d568-127">Comunicazione da client a client: la porta TCP 7680 deve essere aperta per il traffico in entrata</span><span class="sxs-lookup"><span data-stu-id="3d568-127">Client to Client communication: TCP port 7680 should be open for inbound traffic</span></span>

### <span data-ttu-id="3d568-128">Sync</span><span class="sxs-lookup"><span data-stu-id="3d568-128">Sync</span></span>

<span data-ttu-id="3d568-129">Questi endpoint consentono di gestire la lettura e la scrittura di dati sincronizzati, la gestione dei diritti per proteggere i dati e notificare il browser quando sono disponibili nuovi dati di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d568-129">These endpoints manage the reading and writing of synced data, rights management for secure data, and notifying the browser when new sync data is available.</span></span>

- <span data-ttu-id="3d568-130">Endpoint del servizio di sincronizzazione Edge:</span><span class="sxs-lookup"><span data-stu-id="3d568-130">Edge sync service endpoints:</span></span>

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- <span data-ttu-id="3d568-131">Endpoint di Azure Information Protection:</span><span class="sxs-lookup"><span data-stu-id="3d568-131">Azure Information Protection endpoints:</span></span>

  - `https://api.aadrm.com` <span data-ttu-id="3d568-132">(per la maggior parte dei tenant)</span><span class="sxs-lookup"><span data-stu-id="3d568-132">(for most tenants)</span></span>
  - `https://api.aadrm.de` <span data-ttu-id="3d568-133">(per i tenant in Germania)</span><span class="sxs-lookup"><span data-stu-id="3d568-133">(for tenants in Germany)</span></span>
  - `https://api.aadrm.cn` <span data-ttu-id="3d568-134">(per i tenant in Cina)</span><span class="sxs-lookup"><span data-stu-id="3d568-134">(for tenants in China)</span></span>

- [<span data-ttu-id="3d568-135">Endpoint del servizio di notifica di Windows</span><span class="sxs-lookup"><span data-stu-id="3d568-135">Windows Notification Service endpoints</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <span data-ttu-id="3d568-136">Altri servizi di supporto del browser</span><span class="sxs-lookup"><span data-stu-id="3d568-136">Other browser support services</span></span>

<span data-ttu-id="3d568-137">Fornisce metadati per le funzionalità del browser come protezione del monitoraggio, elenchi di revoche di certificati e altri aggiornamenti dei componenti del browser.</span><span class="sxs-lookup"><span data-stu-id="3d568-137">Provide metadata for browser features such as tracking protection, certificate revocation lists, and other browser component updates.</span></span> <span data-ttu-id="3d568-138">Fornisce dizionari scaricabili per il controllo ortografico ed elenchi di blocco per gli annunci.</span><span class="sxs-lookup"><span data-stu-id="3d568-138">Provide downloadable spellcheck dictionaries and ad-blocking block lists.</span></span> <span data-ttu-id="3d568-139">Fornisce servizi per supportare le funzionalità del browser come le raccolte, il riempimento automatico e l'archivio delle estensioni.</span><span class="sxs-lookup"><span data-stu-id="3d568-139">Provide services to support browser features such as collections, autofill, and extension store.</span></span>

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <span data-ttu-id="3d568-140">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3d568-140">See also</span></span>

- [<span data-ttu-id="3d568-141">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="3d568-141">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3d568-142">Pagina di destinazione della documentazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d568-142">Microsoft Edge documentation landing page</span></span>](https://docs.microsoft.com/DeployEdge/)
- [<span data-ttu-id="3d568-143">Gestire gli endpoint di connessione per Windows 10 Enterprise, versione 1903</span><span class="sxs-lookup"><span data-stu-id="3d568-143">Manage connection endpoints for Windows 10 Enterprise, version 1903</span></span>](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
