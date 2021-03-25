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
ms.openlocfilehash: b8f793edcc23798199fe5de1bfae912a63468464
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448200"
---
# <a name="allow-list-for-microsoft-edge-endpoints"></a>Elenco Consenti per gli endpoint Microsoft Edge

Microsoft Edge richiede la connettività a Internet per supportare le funzionalità. Questo articolo identifica gli URL di dominio che è necessario aggiungere all'elenco Consenti per garantire le comunicazioni tramite firewall e altri meccanismi di sicurezza.

> [!NOTE]
> Si applica a Microsoft Edge versione 77 o successiva.

## <a name="domain-urls-to-allow"></a>URL di dominio da consentire

Consenti gli URL di dominio seguenti per Microsoft Edge.

### <a name="update-service"></a>Servizio di aggiornamento

Il servizio che Microsoft Edge utilizza per verificare la disponibilità di nuovi aggiornamenti.

- `https://msedge.api.cdp.microsoft.com`

### <a name="experimentation-and-configuration-service"></a>Servizio di sperimentazione e configurazione

- `https://config.edge.skype.com`

### <a name="download-locations-for-microsoft-edge"></a>Siti di download per Microsoft Edge

Siti per il download di Microsoft Edge durante un'installazione iniziale o quando è disponibile un aggiornamento. Il sito di download è determinato dal servizio di aggiornamento.

#### <a name="http"></a>HTTP

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > Per semplificare l'elenco Consenti per i siti di download è possibile usare un carattere jolly: `*.dl.delivery.mp.microsoft.com`

### <a name="download-locations-for-microsoft-edge-extensions"></a>Siti di download per le estensioni di Microsoft Edge

Siti per il download delle estensioni di Microsoft Edge durante un'installazione iniziale o quando è disponibile un aggiornamento. Il sito di download è determinato dal servizio di aggiornamento.

#### <a name="http"></a>HTTP

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > Per semplificare l'elenco Consenti per i siti di download è possibile usare un carattere jolly: `*.dl.delivery.mp.microsoft.com`

### <a name="optionally-for-download-delivery-optimization"></a>Facoltativamente per il download dell'ottimizzazione recapito

Per informazioni sull'ottimizzazione recapito, vedi [Ottimizzazione recapito per gli aggiornamenti di Windows 10](/windows/deployment/update/waas-delivery-optimization).

- Comunicazioni da client a servizio: `*.do.dsp.mp.microsoft.com` (porta HTTP 80, porta HTTPS 443)
- Comunicazione da client a client: la porta TCP 7680 deve essere aperta per il traffico in entrata

### <a name="sync"></a>Sync

Questi endpoint consentono di gestire la lettura e la scrittura di dati sincronizzati, la gestione dei diritti per proteggere i dati e notificare il browser quando sono disponibili nuovi dati di sincronizzazione.

- Endpoint del servizio di sincronizzazione Edge:

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- Endpoint di Azure Information Protection:

  - `https://api.aadrm.com` (per la maggior parte dei tenant)
  - `https://api.aadrm.de` (per i tenant in Germania)
  - `https://api.aadrm.cn` (per i tenant in Cina)

- [Endpoint del servizio di notifica di Windows](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <a name="other-browser-support-services"></a>Altri servizi di supporto del browser

Fornisce metadati per le funzionalità del browser come protezione del monitoraggio, elenchi di revoche di certificati e altri aggiornamenti dei componenti del browser. Fornisce dizionari scaricabili per il controllo ortografico ed elenchi di blocco per gli annunci. Fornisce servizi per supportare le funzionalità del browser come le raccolte, il riempimento automatico e l'archivio delle estensioni.

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Pagina di destinazione della documentazione di Microsoft Edge](./index.yml)
- [Gestire gli endpoint di connessione per Windows 10 Enterprise, versione 1903](/windows/privacy/manage-windows-1903-endpoints)