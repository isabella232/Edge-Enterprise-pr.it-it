---
title: Elenco Consenti per gli endpoint Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 10/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Elenco Consenti per gli endpoint Microsoft Edge
ms.openlocfilehash: 48a3a72e5af3744516e3b72d02b5254ad2e0504a
ms.sourcegitcommit: b32d8d64ae65dc5a46e47b7c34b0211097a0cc65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133121"
---
# Elenco Consenti per gli endpoint Microsoft Edge

Microsoft Edge richiede la connettività a Internet per supportare le funzionalità. Questo articolo identifica gli URL di dominio che è necessario aggiungere all'elenco Consenti per garantire le comunicazioni tramite firewall e altri meccanismi di sicurezza.

> [!NOTE]
> Si applica a Microsoft Edge versione 77 o successiva.

## URL di dominio da consentire

Consenti gli URL di dominio seguenti per Microsoft Edge.

### Servizio di aggiornamento

Il servizio che Microsoft Edge utilizza per verificare la disponibilità di nuovi aggiornamenti.

- `https://msedge.api.cdp.microsoft.com`

### Servizio di sperimentazione e configurazione

- `https://config.edge.skype.com`

### Siti di download per Microsoft Edge

Siti per il download di Microsoft Edge durante un'installazione iniziale o quando è disponibile un aggiornamento. Il sito di download è determinato dal servizio di aggiornamento.

#### HTTP

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### HTTPS

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > Per semplificare l'elenco Consenti per i siti di download è possibile usare un carattere jolly: `*.dl.delivery.mp.microsoft.com`

### Siti di download per le estensioni di Microsoft Edge

Siti per il download delle estensioni di Microsoft Edge durante un'installazione iniziale o quando è disponibile un aggiornamento. Il sito di download è determinato dal servizio di aggiornamento.

#### HTTP

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### HTTPS

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > Per semplificare l'elenco Consenti per i siti di download è possibile usare un carattere jolly: `*.dl.delivery.mp.microsoft.com`

### Facoltativamente per il download dell'ottimizzazione recapito

Per informazioni sull'ottimizzazione recapito, vedi [Ottimizzazione recapito per gli aggiornamenti di Windows 10](https://aka.ms/waas-do).

- Comunicazioni da client a servizio: `*.do.dsp.mp.microsoft.com` (porta HTTP 80, porta HTTPS 443)
- Comunicazione da client a client: la porta TCP 7680 deve essere aperta per il traffico in entrata

### Sync

Questi endpoint consentono di gestire la lettura e la scrittura di dati sincronizzati, la gestione dei diritti per proteggere i dati e notificare il browser quando sono disponibili nuovi dati di sincronizzazione.

- Endpoint del servizio di sincronizzazione Edge:

  - `https://enterprise.edge.activity.windows.com`
  - `https://edge.activity.windows.com`

- Endpoint di Azure Information Protection:

  - `https://api.aadrm.com` (per la maggior parte dei tenant)
  - `https://api.aadrm.de` (per i tenant in Germania)
  - `https://api.aadrm.cn` (per i tenant in Cina)

- [Endpoint del servizio di notifica di Windows](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## Altri servizi di supporto del browser

Fornisce metadati per le funzionalità del browser come protezione del monitoraggio, elenchi di revoche di certificati e altri aggiornamenti dei componenti del browser. Fornisce dizionari scaricabili per il controllo ortografico ed elenchi di blocco per gli annunci. Fornisce servizi per supportare le funzionalità del browser come le raccolte, il riempimento automatico e l'archivio delle estensioni.

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Pagina di destinazione della documentazione di Microsoft Edge](https://docs.microsoft.com/DeployEdge/)
- [Gestire gli endpoint di connessione per Windows 10 Enterprise, versione 1903](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
