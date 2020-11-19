---
title: Prevenzione della perdita di dati in Microsoft Edge
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 11/18/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Prevenzione della perdita di dati (DPL) in Microsoft Edge
ms.openlocfilehash: 72f670caf34a09cdfc7f47575f688c2a39d3c221
ms.sourcegitcommit: 5a5be508c3c9c57187aca821b4a16f639abdd7e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "11176943"
---
# Prevenzione della perdita di dati (DPL) in Microsoft Edge

La prevenzione della perdita dei dati è un sistema di tecnologie che identifica e protegge i dati aziendali sensibili dalla divulgazione non autorizzata. Per conformarsi agli standard aziendali e alle normative di settore, le organizzazioni devono proteggere le informazioni riservate e impedirne la divulgazione non autorizzata. Le informazioni riservate includono dati finanziari o informazioni personali, ad esempio i numeri di carta di credito, i numeri di previdenza sociale o i record sanitari, etc.

Il lavoro da remoto ha posto un maggiore accento sull'utilizzo di DLP. Con l'uso crescente delle attività personali e di lavoro tramite dispositivi, le aziende vedono un rischio maggiore di condivisione non autorizzata di dati aziendali all'esterno del luogo di lavoro.

Questa combinazione di attività utente si è estesa anche ai dispositivi, in cui i dati vengono spostati tra dispositivi personali e aziendali in una vasta gamma di reti pubbliche e private. Il risultato finale è un rischio significativamente maggiore di esposizione dei dati sensibili.

Microsoft Edge supporta in modo nativo due diverse soluzioni DLP, Microsoft Endpoint DLP e Windows Information Protection (WIP).

## Prevenzione della perdita dei dati di Microsoft Endpoint (Endpoint DLP)

Microsoft Endpoint DLP fa parte della nuova generazione di prevenzione della perdita dei dati che usa concetti moderni come la protezione incentrata sui dati. È incorporato in Windows 10 e Microsoft Edge, quindi non ha bisogno di altri agenti o plugin nel dispositivo.

> [!NOTE]
> Si applica a Microsoft Edge versione 85 o successiva.

Per altre informazioni su Endpoint DLP:

- [Scopri di più sulla prevenzione della perdita dei dati di Microsoft 365 Endpoint](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- [Introduzione sulla prevenzione della perdita dei dati di Endpoint](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide)

Microsoft Edge applica i criteri configurati dall'amministratore per i file sensibili e registra gli eventi di controllo per le attività non conformi.

Alcune delle attività utente che è possibile controllare e gestire nei dispositivi che eseguono Windows 10 includono le seguenti:

- Caricamento file: protegge il caricamento di file sensibili in posizioni cloud non autorizzate. I prossimi 3 screenshot mostrano una sequenza in cui un utente tenta di trascinare un file di dati sensibili nella propria archiviazione locale.
- Protezione Appunti: protegge i dati sensibili dalla copia dal file.
- Protezione stampa: proteggere il file riservato dalla stampa.
- Salva su USB / rete: protegge i file sensibili dal salvataggio in un’unità di archiviazione USB rimovibile o in posizioni di rete non autorizzate.

Per informazioni più dettagliate sulle attività degli utenti che è possibile controllare e gestire, vedi [Attività endpoint che è possibile monitorare e su cui si può intervenire](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on).

## Windows Information Protection

Per informazioni su come Microsoft Edge supporta Windows Information Protection (WIP), consulta [Supporto per Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection). Per saperne di più sui requisiti di sistema, i vantaggi e le funzionalità supportate visita le seguenti sezioni:

- [Requisiti di sistema](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [Vantaggi di Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [Funzionalità di Windows Information Protection in Microsoft Edge](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: Prevenzione della perdita di dati - Microsoft Edge](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [Panoramica della prevenzione della perdita di dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)
- [Proteggere i dati aziendali con Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
