---
title: Prevenzione della perdita di dati in Microsoft Edge
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Prevenzione della perdita di dati (DPL) in Microsoft Edge
ms.openlocfilehash: 8c7906f69f8d1161b47aa381bc04bcdaa70fe6cd
ms.sourcegitcommit: c290b0b0fa6b7d7f94dcdfdda91302da733326ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314559"
---
# <span data-ttu-id="dbcdd-103">Prevenzione della perdita di dati (DPL) in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dbcdd-103">Data Loss Prevention (DLP) in Microsoft Edge</span></span>

<span data-ttu-id="dbcdd-104">La prevenzione della perdita dei dati è un sistema di tecnologie che identifica e protegge i dati aziendali sensibili dalla divulgazione non autorizzata.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-104">Data loss prevention (DLP) is a system of technologies that identify and safeguard sensitive enterprise data from unauthorized disclosure.</span></span> <span data-ttu-id="dbcdd-105">Per conformarsi agli standard aziendali e alle normative di settore, le organizzazioni devono proteggere le informazioni riservate e impedirne la divulgazione non autorizzata.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-105">To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its unauthorized disclosure.</span></span> <span data-ttu-id="dbcdd-106">Le informazioni riservate includono dati finanziari o informazioni personali, ad esempio i numeri di carta di credito, i numeri di previdenza sociale o i record sanitari, etc.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-106">Sensitive information includes financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records, among many other things.</span></span>

<span data-ttu-id="dbcdd-107">Il lavoro da remoto ha posto un maggiore accento sull'utilizzo di DLP.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-107">Remote work has increased the emphasis on using DLP.</span></span> <span data-ttu-id="dbcdd-108">Con l'uso crescente delle attività personali e di lavoro tramite dispositivi, le aziende vedono un rischio maggiore di condivisione non autorizzata di dati aziendali all'esterno del luogo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-108">With the growing use of personal and work activities on devices, enterprises are seeing an increased risk of unauthorized sharing of corporate data outside the workplace.</span></span>

<span data-ttu-id="dbcdd-109">Questa combinazione di attività utente si è estesa anche ai dispositivi, in cui i dati vengono spostati tra dispositivi personali e aziendali in una vasta gamma di reti pubbliche e private.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-109">This blending of user activities has spread to devices as well, where data is moved between personal and corporate devices over a variety of public and private networks.</span></span> <span data-ttu-id="dbcdd-110">Il risultato finale è un rischio significativamente maggiore di esposizione dei dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-110">The net result is a dramatically increased risk of exposing sensitive data.</span></span>

<span data-ttu-id="dbcdd-111">Microsoft Edge supporta in modo nativo due diverse soluzioni DLP, Microsoft Endpoint DLP e Windows Information Protection (WIP).</span><span class="sxs-lookup"><span data-stu-id="dbcdd-111">Microsoft Edge natively supports two different DLP solutions, Microsoft Endpoint DLP and Windows Information Protection (WIP).</span></span>

## <span data-ttu-id="dbcdd-112">Prevenzione della perdita dei dati di Microsoft Endpoint (Endpoint DLP)</span><span class="sxs-lookup"><span data-stu-id="dbcdd-112">Microsoft Endpoint data loss prevention (Endpoint DLP)</span></span>

<span data-ttu-id="dbcdd-113">Microsoft Endpoint DLP fa parte della nuova generazione di prevenzione della perdita dei dati che usa concetti moderni come la protezione incentrata sui dati.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-113">Microsoft Endpoint DLP is the next generation of data loss prevention using modern concepts such as data-centric protection.</span></span> <span data-ttu-id="dbcdd-114">È incorporato in Windows 10 e Microsoft Edge, quindi non ha bisogno di altri agenti o plugin nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-114">It's built-in to Windows 10 and Microsoft Edge so it doesn't need additional agents or plugins on the device.</span></span>

> [!NOTE]
> <span data-ttu-id="dbcdd-115">Si applica a Microsoft Edge versione 85 o successiva.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-115">This applies to Microsoft Edge version 85 or later.</span></span>

<span data-ttu-id="dbcdd-116">Per altre informazioni sulla prevenzione della perdita dei dati degli endpoint, usare le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbcdd-116">To learn more about Endpoint DLP, use the following resources:</span></span>

- [<span data-ttu-id="dbcdd-117">Video: Microsoft Edge e prevenzione della perdita dei dati (DLP)</span><span class="sxs-lookup"><span data-stu-id="dbcdd-117">Video: Microsoft Edge and Data loss prevention (DLP)</span></span>](microsoft-edge-video-security-dlp.md)
- [<span data-ttu-id="dbcdd-118">Informazioni sulla prevenzione della perdita dei dati di Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbcdd-118">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide&preserve-view=true)
- [<span data-ttu-id="dbcdd-119">Introduzione sulla prevenzione della perdita dei dati di Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbcdd-119">Get started with Endpoint data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&preserve-view=true)

<span data-ttu-id="dbcdd-120">Microsoft Edge applica i criteri configurati dall'amministratore per i file sensibili e registra gli eventi di controllo per le attività non conformi.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-120">Microsoft Edge enforces admin configured policies for sensitive files and records audit events for non-compliant activities.</span></span>

<span data-ttu-id="dbcdd-121">Alcune delle attività utente che è possibile controllare e gestire nei dispositivi che eseguono Windows 10 includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbcdd-121">Some of the user activities that you can audit and manage on devices running Windows 10 include the following activities:</span></span>

- <span data-ttu-id="dbcdd-122">Caricamento file: protegge il caricamento di file sensibili in posizioni cloud non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-122">File Upload: Protect sensitive file upload to unauthorized cloud locations.</span></span> <!-- The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.-->
- <span data-ttu-id="dbcdd-123">Protezione Appunti: protegge i dati sensibili dalla copia dal file.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-123">Clipboard Protection: Protect sensitive data from being copied out of the file.</span></span>
- <span data-ttu-id="dbcdd-124">Protezione stampa: proteggere il file riservato dalla stampa.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-124">Print Protection: Protect sensitive file from being printed.</span></span>
- <span data-ttu-id="dbcdd-125">Salva su USB / rete: protegge i file sensibili dal salvataggio in un’unità di archiviazione USB rimovibile o in posizioni di rete non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="dbcdd-125">Save to USB/Network: Protect sensitive file from being saved to removable USB storage or unauthorized network locations.</span></span>

<span data-ttu-id="dbcdd-126">Per informazioni più dettagliate sulle attività degli utenti che è possibile controllare e gestire, vedi [Attività endpoint che è possibile monitorare e su cui si può intervenire](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="dbcdd-126">For more detailed information about user activities you can audit and manage, see [Endpoint activities you can monitor and take action on](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on&preserve-view=true).</span></span>

## <span data-ttu-id="dbcdd-127">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="dbcdd-127">Windows Information Protection</span></span>

<span data-ttu-id="dbcdd-128">Per informazioni su come Microsoft Edge supporta Windows Information Protection (WIP), consulta [Supporto per Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection).</span><span class="sxs-lookup"><span data-stu-id="dbcdd-128">Check out [Support for Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection), which describes how Microsoft Edge supports Windows Information Protection (WIP).</span></span> <span data-ttu-id="dbcdd-129">Per saperne di più sui requisiti di sistema, i vantaggi e le funzionalità supportate visita le seguenti sezioni:</span><span class="sxs-lookup"><span data-stu-id="dbcdd-129">You can learn moe about system requirements, benefits, and supported features in the following sections:</span></span>

- [<span data-ttu-id="dbcdd-130">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="dbcdd-130">System Requirements</span></span>](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [<span data-ttu-id="dbcdd-131">Vantaggi di Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="dbcdd-131">Windows Information Protection Benefits</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [<span data-ttu-id="dbcdd-132">Funzionalità di Windows Information Protection in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dbcdd-132">WIP features supported in Microsoft Edge</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## <span data-ttu-id="dbcdd-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbcdd-133">See also</span></span>

- [<span data-ttu-id="dbcdd-134">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbcdd-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="dbcdd-135">Video: Prevenzione della perdita di dati - Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dbcdd-135">Video: Data loss prevention - Microsoft Edge</span></span>](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [<span data-ttu-id="dbcdd-136">Panoramica della prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="dbcdd-136">Overview of data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide&preserve-view=true)
- [<span data-ttu-id="dbcdd-137">Proteggere i dati aziendali con Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="dbcdd-137">Protect your enterprise data using Windows Information Protection</span></span>](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
