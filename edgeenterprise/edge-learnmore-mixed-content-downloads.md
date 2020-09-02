---
title: Microsoft Edge e download di contenuto misto
ms.author: kele
author: dan-wesley
manager: srugh
ms.date: 04/30/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge e download di contenuto misto
ms.openlocfilehash: 57da17a8684b97aad88e7837ff9d070f6862357b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980211"
---
# Informazioni su Microsoft Edge e i download di contenuto misto

Questo articolo illustra i download di contenuto misto e il modo in cui Microsoft Edge li gestisce.

>[!NOTE]
>Questo articolo si applica a Microsoft Edge versione 85 o successiva.

## Cosa sono i download di contenuto misto?

Un download di contenuto misto si verifica quando si avvia il download da una pagina HTML che è stata caricata tramite una connessione HTTPS sicura, ma si verifica una delle condizioni seguenti:

- Uno o più dei reindirizzamenti del percorso di download sono stati caricati tramite una connessione HTTP non sicura.
- Il percorso di download finale è stato caricato tramite una connessione HTTP non sicura.

Entrambi gli scenari sono contenuti misti perché la richiesta è stata eseguita usando il protocollo HTTPS sicuro e sia il contenuto HTTP che quello HTTPS è coinvolto nel raggiungimento della destinazione finale per il download. I browser moderni visualizzano avvisi su questo tipo di contenuto per indicare agli utenti che questo download potrebbe essere trasferito in modo non sicuro, anche se la pagina originale a cui si ha avuto accesso è sicura.

## Avvisi download e opzioni utente

L'avviso download garantisce che gli utenti sappiano che il file scaricato potrebbe essere letto da utenti malintenzionati nella rete. Questo avviso consente a un utente di prendere una decisione ponderata sull'eventuale download del file.

In Microsoft Edge i download di contenuto misto verranno bloccati, ma gli utenti possono ignorare e scaricare il file, se necessario. Microsoft Edge prevede di iniziare a bloccare i download di file eseguibili con contenuto misto a partire da Microsoft Edge versione 85 e bloccherà diversi tipi di file nei rilasci futuri.

> [!NOTE]
> La distribuzione di questa funzionalità è soggetta a modifiche in base alla programmazione del rilascio e al feedback degli utenti.

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

Nella barra di download il messaggio di avviso del blocco avrà l'aspetto seguente.

 ![Avviso contenuto misto nella barra di download](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

Nella pagina di download l’avviso di blocco avrà l’aspetto seguente:

 ![Richiesta di override del contenuto misto](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

Se un utente decide di conservare il download, viene richiesto di confermare l'azione. La schermata seguente mostra un esempio di richiesta di conferma.

 ![Scegli Modalità Internet Explorer](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## Criteri di supporto

Per le aziende che desiderano escludere il blocco del contenuto misto da siti Web specifici, è possibile usare il criterio [InsecureContentAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#insecurecontentallowedforurls).

## Licenza dei contenuti

> [!NOTE]
> Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/). La pagina originale è disponibile [qui](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content).
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
