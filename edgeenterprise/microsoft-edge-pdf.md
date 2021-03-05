---
title: Lettre PDF in Microsoft Edge
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 03/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Informazioni sul lettore PDF in Microsoft Edge.
ms.openlocfilehash: d84b838556ed10951d7a7a3c6e5085b7e32c286c
ms.sourcegitcommit: f14286edec59ee9183bdf38c15fc890881efd64f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385034"
---
# <a name="pdf-reader-in-microsoft-edge"></a>Lettre PDF in Microsoft Edge

I file PDF costituiscono una parte importante delle nostre vite quotidiane. Sono disponibili sotto forma di contratti e accordi, newsletter, moduli, articoli di ricerca, curriculum e così via. Questi file evidenziano la necessità di un lettore di PDF affidabile, sicuro e potente, che può essere usato dalle aziende.

Microsoft Edge include un lettore di PDF incorporato che consente di aprire i file PDF locali, online o incorporati nelle pagine Web. È possibile aggiungere annotazioni a questi file con input penna ed evidenziazione. Questo lettore PDF offre agli utenti una singola applicazione in grado di soddisfare le esigenze di pagine Web e documenti PDF. Il lettore PDF di Microsoft Edge è un'applicazione sicura e affidabile che funziona nelle piattaforme desktop di Windows e macOS.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge, versione 77 o successiva.

## <a name="prerequisites-support-and-constraints"></a>Prerequisiti, supporto e limiti

Nella tabella che segue vengono indicati i canali e le versioni di Microsoft Edge supportati da ogni lettore PDF.

| Funzionalità | Versione canale Stable |
|---------|------------------------|
| Visualizzare e stampare file PDF locali, online e incorporati | 79.0.309.71                |
| Compilazione moduli base<br>(I moduli JavaScript non sono supportati) | 79.0.309.71           |
|Sommario| 86.0.622.38 |
| Visualizzazione pagina |Promozione in corso ai canali [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) |
| Modalità navigazione con cursore |87.0.664.41 |
| Input penna  | 80.0.361.48            |
| Personalizzazione input penna | 83.0.478.54  |
| Highlight  | 81.0.416.53         |
| Note di testo | Promozione in corso ai canali [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) |
| Leggi ad alta voce | 84.0.522.63  |
| Visualizzare i file protetti di Microsoft Information Protection (MIP) | Supporto Windows in 80.0.361.48<br>Supporto Mac in 81.0.416.53 |
|  Visualizzare i file protetti con Information Rights Management (IRM)  | 83.0.478.37            |
| Visualizzare e convalidare firme digitali | Disponibile nei canali Canary e Dev. Ci stiamo lavorando attivamente. |

### <a name="constraints"></a>Vincoli

Limiti del lettore PDF corrente:

-  XML Forms Architecture (XFA) è un formato legacy di moduli non supportati in Microsoft Edge.
-  La documentazione relativa agli scenari di accessibilità attualmente non supportati sono disponibili nel blog sui [Report Microsoft sulla conformità agli standard di accessibilità](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/).

## <a name="features"></a>Funzionalità

Il lettore PDF, integrato in Microsoft Edge, include le caratteristiche di base per la lettura e la navigazione, come zoom, ruota, adatta alla pagina/larghezza, passa alla pagina e cerca, tra gli altri. È possibile accedervi tramite una barra degli strumenti appuntabile nella parte superiore del contenuto PDF. Questa sezione offre una panoramica di alcune importanti funzioni. Nella schermata successiva viene visualizzata la barra degli strumenti del lettore PDF.

![Barra degli strumenti lettore PDF](media/microsoft-edge-pdf/pdf-reader-toolbar.png)

### <a name="table-of-contents"></a>Sommario

Sommario consente agli utenti di spostarsi facilmente tra i documenti PDF con un sommario. Quando un utente fa clic sull'icona Sommario, viene visualizzato un riquadro di spostamento in cui è visualizzato un elenco delle sezioni etichettate e delle sottosezioni nel documento PDF. L'utente può quindi fare clic su una delle etichette nel riquadro per passare alla sezione del documento. Il riquadro rimane aperto per tutto il tempo necessario e può essere chiuso quando l'utente vuole tornare a leggere il documento. La schermata successiva mostra il riquadro di spostamento per un documento aperto.

![Navigazione in lettura PDF con Sommario](media/microsoft-edge-pdf/pdf-reader-toc.png)

### <a name="page-view"></a>Visualizzazione pagina

Microsoft Edge supporta visualizzazioni diverse per i documenti PDF nei canali Dev e Canary. Gli utenti possono modificare il layout di un documento da una singola visualizzazione pagina a due pagine visualizzate affiancate. Per modificare la modalità di visualizzazione del documento PDF, gli utenti possono fare clic sul pulsante visualizzazione pagina nella barra degli strumenti PDF e quindi scegliere la visualizzazione che si vuole usare. Nella schermata successiva verrà visualizzata la visualizzazione due pagine.

![Lettore PDF con due visualizzazioni di pagina del documento.](media/microsoft-edge-pdf/pdf-reader-page-view.png)

### <a name="caret-mode-browsing"></a>Modalità navigazione con cursore

L'esplorazione del cursore è disponibile per i file PDF aperti in Microsoft Edge, il che significa che gli utenti possono interagire con i file PDF usando la tastiera. Se un utente preme il tasto F7 in qualsiasi punto del browser, viene chiesto se la navigazione con cursore deve essere attivata. Se abilitata, la navigazione con cursore è disponibile per qualsiasi contenuto aperto nel browser, sia esso file PDF o pagine Web. Quando un utente preme di nuovo F7, la navigazione con cursore è disattivata. Quando la navigazione con cursore è attiva e il focus è sul contenuto, gli utenti vedranno un cursore lampeggiante nel file PDF. Il cursore può essere usato anche per spostarsi nel file o per selezionare il testo premendo MAIUSC mentre si sposta il puntatore del mouse. Questa funzionalità consente agli utenti di creare facilmente elementi come evidenziazioni o interagire con elementi come collegamenti o campi modulo con la tastiera. La schermata successiva mostra il menu di scelta rapida per attivare la modalità di navigazione con cursore.

![Menu Lettore PDF per la modelità di navigazione con cursore.](media/microsoft-edge-pdf/pdf-reader-caret-mode.png)

### <a name="inking"></a>Input penna

L'input penna nei file PDF è utile per scrivere note veloci per rapidi riferimenti, per firmare o compilare moduli PDF. Questa funzionalità è ora disponibile in Microsoft Edge. Oltre a usare l'input penna nei file PDF, se necessario, è possibile usare il colore e il tratto input penna per attirare l'attenzione su parti specifiche del file PDF. Lo screenshot seguente mostra il modo in cui un utente può aggiungere l'input penna a una pagina PDF.

![Aggiungere un input penna a una pagina PDF](media/microsoft-edge-pdf/pdf-reader-inking.png)

### <a name="highlight"></a>Highlight

Il lettore PDF in Microsoft Edge include il supporto per l'aggiunta e la modifica di evidenziazioni. Per creare un'evidenziazione, l'utente deve semplicemente selezionare il testo, fare clic con il pulsante destro del mouse su di esso, selezionare evidenziazioni nel menu e scegliere il colore desiderato. Le evidenziazioni possono essere create anche con una penna o una tastiera. Lo screenshot seguente mostra le opzioni di evidenziazione disponibili.

![Usare l'opzione di evidenziazione nel lettore PDF](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### <a name="text-notes"></a>Note di testo

Durante la lettura di un file PDF, le note di testo possono essere aggiunte al testo nel file per annotare i pensieri per ritrovarle facilmente in un secondo momento.

Gli utenti possono aggiungere una nota selezionando la porzione di testo a cui si vuole aggiungere una nota e richiamando il menu di scelta rapida per fare clic con il pulsante destro del mouse. Selezionando l'opzione **Aggiungi commento** nel menu si aprirà una casella di testo in cui gli utenti possono aggiungere i loro commenti. È possibile digitare il commento e quindi fare clic sul segno di spunta per salvare il commento.

Dopo l'aggiunta di una nota, il testo selezionato verrà evidenziato e verrà visualizzata un'icona di commento per indicare il commento. Gli utenti possono posizionare il puntatore del mouse sull'icona per visualizzare in anteprima il commento o fare clic su di esso per aprire e modificare la nota.

Nella schermata successiva viene visualizzata una nota che verrà aggiunta al testo evidenziato.

![Lettore PDF aggiunge una nota di testo al documento.](media/microsoft-edge-pdf/pdf-reader-text-note.png)

### <a name="read-aloud"></a>Leggi ad alta voce

Leggi ad alta voce per PDF consente agli utenti di ascoltare il contenuto del PDF durante l'esecuzione di altre importanti attività. Aiuta anche gli studenti a concentrarsi sul contenuto, facilitando l'apprendimento. Nella schermata successiva viene illustrato un esempio di lettura ad alta voce. L'evidenziazione mostra il testo che si sta leggendo al momento.

![Usare l'opzione evidenzia per Leggi ad alta voce nel lettore PDF](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### <a name="protected-pdfs"></a>PDF protetti

[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide&preserve-view=true) consente agli utenti di collaborare con altri in tutta sicurezza, rispettando al contempo i criteri di conformità dell'organizzazione. Una volta protetto un file, le azioni che gli utenti possono intraprendere sono determinate dalle autorizzazioni assegnate.

> [!IMPORTANT]
> È necessaria una licenza per MIP. Per altre informazioni, vedere le [istruzioni per la gestione delle licenze di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

Questi file possono essere aperti direttamente nel browser, senza la necessità di scaricare altri software o installare alcun componente aggiuntivo. Questa funzionalità integra la sicurezza fornita da MIP direttamente nel browser, offrendo un flusso di lavoro senza soluzione di continuità.

![Documento PDF protetto.](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

Oltre ai file protetti MIP, è possibile aprire anche file PDF nelle raccolte SharePoint [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide&preserve-view=true) in modalità nativa nel browser.

Microsoft Edge consente agli utenti di visualizzare i file protetti MIP salvati in locale o nel cloud. Se salvato localmente, il file può essere aperto direttamente nel browser. Se il file viene aperto da un servizio cloud come SharePoint, è possibile che l'utente debba usare l'opzione "Apri nel browser".

Se il profilo con cui l'utente ha eseguito l'accesso a Microsoft Edge dispone almeno delle autorizzazioni di visualizzazione per il file, il file verrà aperto in Microsoft Edge.

![Chiedere conferma per il salvataggio delle pagine PDF di SharePoint protette da MIP](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

### <a name="view-and-validate-certificate-based-digital-signatures"></a>Visualizzare e convalidare firme digitali basate su certificati

In questo mondo digitale, diventa importante stabilire l'autenticità e la proprietà del contenuto nel documento. Le firme digitali basate su certificati vengono comunemente usate nei documenti PDF per assicurarti che il contenuto del documento sia uguale a quello previsto dall'autore e che non sia stato modificato. Microsoft Edge consente di visualizzare e convalidare le firme digitali dei certificati nei file PDF.

Stiamo lavorando attivamente per migliorare il supporto per affrontare altri scenari e non vediamo l'ora di ricevere feedback.

## <a name="accessibility"></a>Accessibilità

Il lettore PDF include il supporto per l'accessibilità tramite tastiera, la modalità a contrasto elevato e l'utilità per la lettura dello schermo per dispositivi Windows e macOS.

### <a name="keyboard-accessibility"></a>Accessibilità tramite tastiera

Gli utenti possono usarla per spostarsi tra le diverse parti del documento con cui un utente può interagire, come i campi modulo e le evidenziazioni, tramite la tastiera. Gli utenti possono anche usare la modalità cursore per spostarsi e interagire con i file PDF usando la tastiera.

### <a name="high-contrast-mode"></a>Modalità a contrasto elevato

Il lettore PDF userà le impostazioni definite a livello del sistema operativo per il rendering del contenuto PDF in modalità a contrasto elevato.

### <a name="screen-reader-support"></a>Utilità per la lettura dello schermo

Gli utenti possono esplorare e leggere i file PDF usando le utilità per la lettura dello schermo su computer Windows e Mac.

## <a name="security-and-reliability"></a>Sicurezza e affidabilità

La sicurezza è alla base di qualsiasi organizzazione. La sicurezza dei lettori PDF è al centro della progettazione della sicurezza di Microsoft Edge. Due delle funzionalità di sicurezza più importanti di un lettore di PDF sono l'isolamento dei processi e Microsoft Defender Application Guard (Application Guard).

- Isolamento del processo. I file PDF aperti da diversi siti Web vengono elaborati in modo completamente isolato. Il browser non deve comunicare con alcun sito Web o file PDF aperti da un'altra origine. La navigazione PDF è protetta da qualsiasi attacco che intenda usare i PDF compromessi come superficie d'attacco.

- Application Guard: Con Application Guard, gli amministratori possono impostare un elenco dei siti attendibili per la propria organizzazione. Qualsiasi altro sito aperto dagli utenti verrà aperto in una finestra separata di Application Guard ed eseguito nel loro contenitore. Il contenitore protegge la rete aziendale e i dati del computer dell'utente da eventuali compromissioni.<br><br>
Questa protezione si applica anche a tutti i file PDF online che vengono visualizzati. Inoltre, tutti i file PDF scaricati da una finestra di Application Guard vengono archiviati e, se necessario, riaperti nel contenitore. Ciò consente di proteggere l'ambiente non solo quando il file viene scaricato, ma durante tutto il suo ciclo di vita. Per altre informazioni, vedere [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard).

### <a name="reliability"></a>Affidabilità

Dato che Microsoft Edge si basa su Chromium, gli utenti possono aspettarsi lo stesso livello di affidabilità a cui sono abituati con altri browser basati su Chromium.

## <a name="deploy-and-update-pdf-reader"></a>Distribuire e aggiornare il lettore PDF

Il lettore PDF viene distribuito e aggiornato con il resto del browser Microsoft Edge. Per maggiori informazioni sulla distribuzione di Microsoft Edge, guarda il video [Distribuzione di Microsoft Edge sui dispositivi](microsoft-edge-video-deploy.md) . È inoltre possibile trovare maggiori informazioni sulla distribuzione nella pagina di destinazione di [Microsoft Edge](https://docs.microsoft.com/DeployEdge/).

> [!TIP]
> È possibile rendere Microsoft Edge il lettore PDF predefinito per l'organizzazione. A tale scopo, [seguire questi passaggi](https://docs.microsoft.com/deployedge/edge-default-browser).

## <a name="roadmap-and-feedback"></a>Roadmap e feedback

La roadmap per il lettore PDF in Microsoft Edge è disponibile [qui](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667).

Stiamo esaminando attivamente i commenti e i suggerimenti sulle funzionalità più richieste. È possibile inviare commenti e suggerimenti tramite il forum di [Microsoft Edge Insider.](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider)

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)
- [Video: Lettore PDF professionale di Microsoft Edge](microsoft-edge-video-pdf-reader.md)