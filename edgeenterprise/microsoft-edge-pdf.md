---
title: Lettre PDF in Microsoft Edge
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 08/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Informazioni sul lettore PDF in Microsoft Edge.
ms.openlocfilehash: c189bc08d4af0c9d5c4d9c573e0b5b7ef32a7fb3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980293"
---
# Lettre PDF in Microsoft Edge

I file PDF costituiscono una parte importante della nostra vita quotidiana. Sono disponibili sotto forma di contratti e accordi, newsletter, moduli, articoli di ricerca, curriculum e così via. Questi file evidenziano la necessità di un lettore di PDF affidabile, sicuro e potente, che può essere usato dalle aziende.

Microsoft Edge include un lettore di PDF incorporato che consente di aprire i file PDF locali, online o incorporati nelle pagine Web. È possibile aggiungere annotazioni a questi file con input penna ed evidenziazione. Questo lettore PDF offre agli utenti una singola applicazione in grado di soddisfare le esigenze di pagine Web e documenti PDF. Il lettore PDF di Microsoft Edge è un'applicazione sicura e affidabile che funziona nelle piattaforme desktop di Windows e macOS.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge, versione 77 o successiva.

## Prerequisiti, supporto e limiti

Nella tabella che segue vengono indicati i canali e le versioni di Microsoft Edge supportati da ogni lettore PDF.

| Funzionalità | Versione canale Stable |
|---------|------------------------|
| Visualizzare e stampare file PDF locali, online e incorporati | 79.0.309.71                |
| Compilazione moduli base<br>(I moduli JavaScript non sono supportati) | 79.0.309.71           |
| Input penna  | 80.0.361.48            |
| Personalizzazione input penna | 83.0.478.54  |
| Highlight  | 81.0.416.53         |
| Leggi ad alta voce | Promozione in corso ai canali [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) |
| Visualizzare i file MIP protetti | Supporto Windows in 80.0.361.48<br>Supporto Mac in 81.0.416.53 |
|  Visualizzare i file IRM protetti  | 83.0.478.37            |

### Vincoli

Limiti del lettore PDF corrente:

-  XML Forms Architecture (XFA) è un formato legacy di moduli non supportati in Microsoft Edge.
-  La documentazione relativa agli scenari di accessibilità attualmente non supportati sono disponibili nel blog sui [Report Microsoft sulla conformità agli standard di accessibilità](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/).

## Funzionalità

### Input penna

L'input penna nei file PDF è utile per scrivere note veloci per rapidi riferimenti, per firmare o compilare moduli PDF. Questa funzionalità è ora disponibile in Microsoft Edge. Oltre a usare l'input penna nei file PDF, se necessario, è possibile usare il colore e il tratto input penna per attirare l'attenzione su parti specifiche del file PDF. Lo screenshot seguente mostra il modo in cui un utente può aggiungere l'input penna a una pagina PDF.

<!-- SCREENSHOT -->
![Aggiungere un input penna a una pagina PDF](media/microsoft-edge-pdf/pdf-reader-inking.png)

### Highlight

Il lettore PDF in Microsoft Edge include il supporto per l'aggiunta e la modifica di evidenziazioni. Per creare un'evidenziazione, l'utente deve semplicemente selezionare il testo, fare clic con il pulsante destro del mouse su di esso, selezionare evidenziazioni nel menu e scegliere il colore desiderato. Lo screenshot seguente mostra le opzioni di evidenziazione disponibili.

![Usare l'opzione di evidenziazione nel lettore PDF](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### Leggi ad alta voce

Leggi ad alta voce per PDF consente agli utenti di ascoltare il contenuto del PDF durante l'esecuzione di altre importanti attività. Aiuta anche gli studenti a concentrarsi sul contenuto, facilitando l'apprendimento. Lo screenshot seguente mostra un esempio di Leggi ad alta voce. L'evidenziazione mostra il testo che si sta leggendo al momento.

![Usare l'opzione di evidenziazione nel lettore PDF](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### PDF protetti

[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) consente agli utenti di collaborare con altri in tutta sicurezza, rispettando al contempo i criteri di conformità dell'organizzazione. Una volta protetto un file, le azioni che gli utenti possono intraprendere sono determinate dalle autorizzazioni assegnate.

Questi file possono essere aperti direttamente nel browser, senza la necessità di scaricare altri software o installare alcun componente aggiuntivo. La sicurezza fornita dal MIP viene così integrata, fornendo un flusso di lavoro senza interruzioni.

<!-- SCREENSHOT -->
![Documento PDF protetto.](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

Oltre ai file protetti MIP, è possibile aprire anche file PDF nelle raccolte SharePoint [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) in modalità nativa nel browser.

Microsoft Edge consente agli utenti di visualizzare i file protetti MIP salvati in locale o nel cloud. Se salvato localmente, il file può essere aperto direttamente nel browser. Se il file viene aperto da un servizio cloud come SharePoint, è possibile che l'utente debba usare l'opzione "Apri nel browser".

Se il profilo con cui l'utente ha eseguito l'accesso a Microsoft Edge dispone almeno delle autorizzazioni di visualizzazione per il file, il file verrà aperto in Microsoft Edge.

<!-- SCREENSHOT -->
![Chiedere conferma per il salvataggio delle pagine PDF di SharePoint protette da MIP](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

## Accessibilità

Il lettore PDF include il supporto per l'accessibilità tramite tastiera, la modalità a contrasto elevato e l'utilità per la lettura dello schermo per dispositivi Windows e macOS.

### Accessibilità tramite tastiera

Gli utenti possono usarla per spostarsi tra le diverse parti del documento con cui un utente può interagire, come i campi modulo e le evidenziazioni, tramite la tastiera.

<!-- SCREENSHOT -->

### Modalità a contrasto elevato

Il lettore PDF userà le impostazioni definite a livello del sistema operativo per il rendering del contenuto PDF in modalità a contrasto elevato.

<!-- SCREENSHOT -->
<!--![High contrast mode for pdf file](media/microsoft-edge-pdf/pdf-reader-high-contrast.png)-->

### Utilità per la lettura dello schermo

Gli utenti possono esplorare e leggere i file PDF usando le utilità per la lettura dello schermo su computer Windows e Mac. <!--The next screenshot shows the toolbar that users can use for audio settings when they're using the Read Aloud option in PDF reader. -->

<!-- SCREENSHOT -->
<!--
![Screen reader toolbar](media/microsoft-edge-pdf/pdf-reader-read-aloud.png) -->

## Sicurezza e affidabilità

La sicurezza è alla base di qualsiasi organizzazione. La sicurezza dei lettori PDF è al centro della progettazione della sicurezza di Microsoft Edge. Due delle funzionalità di sicurezza più importanti di un lettore di PDF sono l'isolamento dei processi e Microsoft Defender Application Guard (Application Guard).

- Isolamento del processo. I file PDF aperti da diversi siti Web vengono elaborati in modo completamente isolato. Il browser non deve comunicare con alcun sito Web o file PDF aperti da un'altra origine. La navigazione PDF è protetta da qualsiasi attacco che intenda usare i PDF compromessi come superficie d'attacco.

- Application Guard: Con Application Guard, gli amministratori possono impostare un elenco dei siti attendibili per la propria organizzazione. Qualsiasi altro sito aperto dagli utenti verrà aperto in una finestra separata di Application Guard ed eseguito nel loro contenitore. Il contenitore protegge la rete aziendale e i dati del computer dell'utente da eventuali compromissioni.<br><br>
Questa protezione si applica anche a tutti i file PDF online che vengono visualizzati. Inoltre, tutti i file PDF scaricati da una finestra di Application Guard vengono archiviati e, se necessario, riaperti nel contenitore. Ciò consente di proteggere l'ambiente non solo quando il file viene scaricato, ma durante tutto il suo ciclo di vita. Per altre informazioni, vedere [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard).

### Affidabilità

Dato che Microsoft Edge si basa su Chromium, gli utenti possono aspettarsi lo stesso livello di affidabilità di Google Chrome.

## Distribuire e aggiornare il lettore PDF

Il lettore PDF viene distribuito e aggiornato con il resto del browser Microsoft Edge. Per maggiori informazioni sulla distribuzione di Microsoft Edge, guarda il video [Distribuzione di Microsoft Edge sui dispositivi](microsoft-edge-video-deploy.md) . È inoltre possibile trovare maggiori informazioni sulla distribuzione nella pagina di destinazione di [Microsoft Edge](https://docs.microsoft.com/DeployEdge/).

> [!TIP]
> È possibile rendere Microsoft Edge il lettore PDF predefinito per l'organizzazione. A tale scopo, [seguire questi passaggi](https://docs.microsoft.com/deployedge/edge-default-browser).

## Roadmap e feedback

La roadmap per il lettore PDF in Microsoft Edge è disponibile [qui](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667).

Stiamo esaminando attivamente i commenti e i suggerimenti sulle funzionalità più richieste. È possibile inviare commenti e suggerimenti tramite [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) e il forum [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider).

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)