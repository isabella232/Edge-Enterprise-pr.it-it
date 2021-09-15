---
title: Prevenzione della perdita di dati in Microsoft Edge
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Prevenzione della perdita di dati (DPL) in Microsoft Edge
ms.openlocfilehash: acbc9dab14c193f4f7cb06eb61e676083bfdf6ef
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980185"
---
# <a name="data-loss-prevention-dlp-in-microsoft-edge"></a>Prevenzione della perdita di dati (DPL) in Microsoft Edge

La prevenzione della perdita dei dati è un sistema di tecnologie che identifica e protegge i dati aziendali sensibili dalla divulgazione non autorizzata. Per conformarsi agli standard aziendali e alle normative di settore, le organizzazioni devono proteggere le informazioni riservate e impedirne la divulgazione non autorizzata. Le informazioni riservate includono dati finanziari o informazioni personali, ad esempio i numeri di carta di credito, i numeri di previdenza sociale o i record sanitari, etc.

Il lavoro da remoto ha posto un maggiore accento sull'utilizzo di DLP. Con l'uso crescente delle attività personali e di lavoro tramite dispositivi, le aziende vedono un rischio maggiore di condivisione non autorizzata di dati aziendali all'esterno del luogo di lavoro.

Questa combinazione di attività utente si è estesa anche ai dispositivi, in cui i dati vengono spostati tra dispositivi personali e aziendali in una vasta gamma di reti pubbliche e private. Il risultato finale è un rischio significativamente maggiore di esposizione dei dati sensibili.

Microsoft Edge supporta in modo nativo due diverse soluzioni DLP, Microsoft Endpoint DLP e Windows Information Protection (WIP).

## <a name="microsoft-endpoint-data-loss-prevention-endpoint-dlp"></a>Prevenzione della perdita dei dati di Microsoft Endpoint (Endpoint DLP)

Microsoft Endpoint DLP fa parte della nuova generazione di prevenzione della perdita dei dati che usa concetti moderni come la protezione incentrata sui dati. È incorporato in Windows 10 e Microsoft Edge, quindi non ha bisogno di altri agenti o plugin nel dispositivo.

> [!NOTE]
> Si applica a Microsoft Edge versione 85 o successiva.

Per altre informazioni sulla prevenzione della perdita dei dati degli endpoint, usare le risorse seguenti:

- [Video: Microsoft Edge e prevenzione della perdita dei dati (DLP)](microsoft-edge-video-security-dlp.md)
- [Informazioni sulla prevenzione della perdita dei dati di Microsoft 365 Endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide)
- [Introduzione sulla prevenzione della perdita dei dati di Endpoint](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide)

Microsoft Edge applica i criteri configurati dall'amministratore per i file sensibili e registra gli eventi di controllo per le attività non conformi.

Alcune delle attività utente che è possibile controllare e gestire nei dispositivi che eseguono Windows 10 includono le seguenti:

- Caricamento file: protegge il caricamento di file sensibili in posizioni cloud non autorizzate. <!-- The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.-->
- Protezione Appunti: protegge i dati sensibili dalla copia dal file.
- Protezione stampa: proteggere il file riservato dalla stampa.
- Salva su USB / rete: protegge i file sensibili dal salvataggio in un’unità di archiviazione USB rimovibile o in posizioni di rete non autorizzate.

Per informazioni più dettagliate sulle attività degli utenti che è possibile controllare e gestire, vedi [Attività endpoint che è possibile monitorare e su cui si può intervenire](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on).

## <a name="windows-information-protection"></a>Windows Information Protection

Per informazioni su come Microsoft Edge supporta Windows Information Protection (WIP), consulta [Supporto per Windows Information Protection](./microsoft-edge-security-windows-information-protection.md). Per saperne di più sui requisiti di sistema, i vantaggi e le funzionalità supportate visita le seguenti sezioni:

- [Requisiti di sistema](./microsoft-edge-security-windows-information-protection.md#system-requirements)
- [Vantaggi di Windows Information Protection](./microsoft-edge-security-windows-information-protection.md#windows-information-protection-benefits)
- [Funzionalità di Windows Information Protection in Microsoft Edge](./microsoft-edge-security-windows-information-protection.md#wip-features-supported-in-microsoft-edge)

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: Prevenzione della perdita di dati - Microsoft Edge](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [Panoramica della prevenzione della perdita di dati](/microsoft-365/compliance/data-loss-prevention-policies?preserve-view=true&view=o365-worldwide)
- [Proteggere i dati aziendali con Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)