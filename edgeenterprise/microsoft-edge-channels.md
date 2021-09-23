---
title: Panoramica dei canali di Microsoft Edge
ms.author: srugh
author: RyanHechtMSFT
manager: seanlynd
ms.date: 09/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Panoramica dei canali di Microsoft Edge
ms.openlocfilehash: dd65d932950be90d3d9278fa41ae843335b2074d
ms.sourcegitcommit: 8e5294e82cf62abc916cfd24692f55925330d42b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "12037189"
---
# <a name="overview-of-the-microsoft-edge-channels"></a>Panoramica dei canali di Microsoft Edge

Uno dei vantaggi della versione successiva di Microsoft Edge è che Microsoft può fornire le nuove funzionalità su base regolare. Tuttavia, in qualità di amministratore che distribuisce Microsoft Edge agli utenti dell'organizzazione potresti volere un controllo maggiore sulla frequenza con cui gli utenti scaricano queste nuove funzionalità. Microsoft offre quattro opzioni, denominate canali, per controllare la frequenza con cui Microsoft Edge viene aggiornato con le nuove funzionalità. Ecco una panoramica delle quattro opzioni.

Per altre informazioni sul supporto per ciascun canale, vedi: [Ciclo di vita di Microsoft Edge](/deployedge/microsoft-edge-support-lifecycle)
  
> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="channel-overview"></a>Panoramica dei canali

|Canale|Scopo principale|Frequenza di aggiornamento con le nuove funzionalità|Con supporto?|
|:---:|---|:---:|:---:|
|[Stable](#stable-channel)|Distribuzione ampia|~4 settimane|Sì|
|[Extended Stable](#extended-stable-channel)|Opzione di rilascio aziendale per Stable allineata a un ciclo di rilascio più lungo |~8 settimane|Sì|
|[Beta](#beta-channel)|Convalida rappresentativa nell'organizzazione|~4 settimane|Sì|
|[Dev](#dev-channel)|Pianificazione e sviluppo|Ogni settimana|No|
|[Canary](#canary-channel)|Contenuto rischioso|Ogni giorno|No|

Il canale di aggiornamento che decidi di distribuire agli utenti dipende da diversi fattori, ad esempio il numero di applicazioni line-of-business che l'utente usa e che devi testare ogni volta che hanno una versione aggiornata di Microsoft Edge. Per prendere questa decisione, esamina le informazioni che seguono sui quattro canali di aggiornamento disponibili per Microsoft Edge.

### <a name="stable-channel"></a>Canale Stable

Il canale Stable è progettato per la distribuzione generale nell'organizzazione ed è il canale in cui la maggior parte degli utenti deve essere attiva. È il più stabile dei canali ed è il risultato della stabilizzazione del set di funzionalità disponibile nella versione precedente del Canale beta. Le nuove funzionalità vengono disponibili circa ogni 4 settimane. Gli aggiornamenti della sicurezza e della qualità vengono forniti in base alle esigenze. Viene fornito il supporto per una versione del canale Stable fino a quando non è disponibile la versione successiva del canale.

### <a name="beta-channel"></a>Canale Beta

Il canale Beta è destinato alla distribuzione della produzione dell'organizzazione a un campione rappresentativo di utenti. Si tratta di una versione con supporto e ogni versione Beta verrà supportata fino a quando non sarà disponibile la versione successiva di questo canale. Si tratta di una buona opportunità per verificare che le operazioni funzionino come previsto nell'ambiente in uso e se si verifica un problema, è necessario porvi rimedio prima di pubblicare la versione nel canale Stable. Le nuove funzionalità vengono disponibili circa ogni 4 settimane. Gli aggiornamenti della sicurezza e della qualità vengono forniti in base alle esigenze.

### <a name="dev-channel"></a>Canale Dev

Il canale Dev intende aiutarti a pianificare e sviluppare con le funzionalità più recenti di Microsoft Edge, ma con una qualità superiore a quella del canale Canary. Questa è la tua opportunità per dare un'occhiata in anteprima alle novità in arrivo e per prepararti per la prossima versione Beta.

### <a name="canary-channel"></a>Canale Canary

Il canale Canary viene distribuito ogni giorno ed è il più rischioso di tutti i canali. Se si desidera accedere agli investimenti più recenti, questi verranno visualizzati per primi qui. A causa della natura di questa cadenza, si verificano problemi di straordinario, quindi è possibile che si desideri installare un altro canale affiancato se si stanno sfruttando i rilasci canarini.

### <a name="extended-stable-channel"></a>Canale stabile esteso

A differenza dei canali di anteprima (Canary, Dev e Beta), il Canale stabile esteso non è disponibile come applicazione browser separata. si tratta invece di un'opzione di rilascio enterprise per l'applicazione Microsoft Edge Stable allineata a un ciclo di rilascio principale di 8 settimane più lungo (a differenza del ciclo di rilascio principale di 4 settimane disponibile in Stable). Anche se ti consigliamo di aggiornare automaticamente Stable nel ciclo di rilascio di 4 settimane, Extended Stable esiste per servire in modo più efficace le organizzazioni che potrebbero richiedere una tempistica più lunga per testare e convalidare nuove versioni del browser.

L'opzione del ciclo di rilascio "Extended Stable" di 8 settimane __ per Microsoft Edge Stable offre aggiornamenti cumulativi delle funzionalità allineati alle versioni pari che iniziano con Microsoft Edge 94; eventuali aggiornamenti delle funzionalità da rilasci dispari verranno pacchettizzati e recapitati come parte della successiva versione con numerazione pari. Ad esempio, se un'organizzazione seleziona il ciclo di rilascio "Extended Stable" di 8 settimane con Microsoft Edge 94, riceverà gli aggiornamenti delle funzionalità successivi con Microsoft Edge 96, Microsoft Edge 98 e così via. Anche se gli aggiornamenti delle funzionalità vengono in pacchetto e recapitati con nuove versioni in base al ciclo di rilascio selezionato, le patch e le correzioni di sicurezza importanti verranno recapitate in base alle esigenze indipendentemente dall'opzione di rilascio selezionata per mantenere la sicurezza del browser. I clienti possono acconsentire esplicitamente all'opzione di rilascio Extended Stable in qualsiasi momento e saranno effettive con la prossima versione di Extended Stable.

![Esempio di confronto Microsoft Edge opzioni del ciclo di rilascio Stable ed Extended Stable.](./media/microsoft-edge-channels/extended-stable-explainer.png)

#### <a name="opting-in-to-the-extended-stable-release-cadence"></a>Consenso esplicito alla cadenza di rilascio stabile estesa

##### <a name="opting-in-to-extended-stable-on-windows-with-automatic-updates-recommended"></a>Acconsentire esplicitamente a Extended Stable Windows aggiornamenti automatici (scelta consigliata)

Se si aggiorna automaticamente Microsoft Edge, è possibile utilizzare gli oggetti Criteri di gruppo per acconsentire esplicitamente alla Cadenza rilascio stabile estesa. [Seguire questa guida](/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template) per ulteriori informazioni sul download e l'installazione dei modelli amministrativi Microsoft Edge criteri di gruppo più recenti.

1. Aprire l'Editor Criteri di gruppo locali e passare a _Configurazione computer>Modelli amministrativi>Microsoft Edge Update>Applicazioni>Microsoft Edge>_.
2. Seleziona **Sostituzione canale di destinazione** e quindi seleziona **Abilitato.**
3. In **Opzioni**seleziona **"Stabile estesa"** nell'elenco a discesa Criteri.

Quando viene rilasciato il successivo aggiornamento al canale Extended Stable con un numero di versione superiore a quello attualmente installato nel dispositivo, Microsoft Edge si aggiornerà automaticamente nel canale Stable esteso. La stringa della `edge://settings/help` versione su indicherà che è in esecuzione un canale diverso.

> [!NOTE]
> Il consenso esplicito a Extended Stable avrà effetto quando nel canale Extended Stable è presente un nuovo aggiornamento con un numero di versione maggiore (principale o secondario) rispetto a quello attualmente installato nel dispositivo. Se si esegue la versione più recente di Microsoft Edge Stable e si acconsente esplicitamente a Extended Stable, questa avrà effetto con la patch o l'aggiornamento successivo di Microsoft Edge.
>
> Per impostazione predefinita, Microsoft Edge non verrà declassato. Se attualmente è in esecuzione una versione con numero dispari di Microsoft Edge Stable, l'opzione di consenso esplicito su Extended Stable significa che non si riceveranno aggiornamenti fino alla successiva versione Microsoft Edge pari.
>
> Se vuoi assicurarti che tutti i dispositivi inizino con una versione specifica di Extended Stable, puoi distribuire la versione specifica di Edge Stable come MSI con il rollback abilitato. Ad esempio, se si desidera iniziare con Extended Stable 94 ma alcuni dispositivi sono già stati aggiornati a Stable 95, è possibile distribuire un file MSI di Edge 94 con il rollback abilitato. Per ulteriori informazioni su come distribuire gli MSI di Edge con il rollback abilitato, vedi la nostra [guida al rollback.](/DeployEdge/edge-learnmore-rollback)

##### <a name="opting-in-to-extended-stable-on-windows-via-intune"></a>Consenso esplicito su Extended Stable Windows tramite Intune

Microsoft Edge I modelli amministrativi possono essere gestiti in modo analogo agli oggetti Criteri di gruppo locali dall'Microsoft Endpoint Manager di amministrazione. Seguire la [guida alla configurazione di Microsoft Edge con Intune](/mem/intune/configuration/administrative-templates-configure-edge). 

**L'impostazione**" Override canale di destinazione " è disponibile nelle sottocartelle "_Microsoft Edge Update >Applicazioni>Microsoft Edge_" . Deve essere impostato su "**Extended Stable**" 

Quando viene rilasciato il successivo aggiornamento al canale Extended Stable con un numero di versione superiore a quello attualmente installato nel dispositivo, Microsoft Edge si aggiornerà automaticamente nel canale Stable esteso. La stringa della `edge://settings/help` versione su indicherà che è in esecuzione un canale diverso.

##### <a name="opting-in-to-extended-stable-on-windows-via-configuration-manager"></a>Consenso esplicito su Extended Stable Windows tramite Configuration Manager

Per altre informazioni su come sincronizzare e approvare Microsoft Edge aggiornamenti in [Configuration Manager,](/mem/configmgr/apps/deploy-use/deploy-edge#update-microsoft-edge) fare riferimento alla guida sull'aggiornamento Microsoft Edge con Configuration Manager.

Gli aggiornamenti stable estesi vengono distribuiti nella raccolta software nella categoria di prodotto "Microsoft Edge", in modo analogo agli aggiornamenti esistenti per i canali Stable, Beta e Dev. Tuttavia, a differenza di Beta e Dev, che si applicano alle proprie applicazioni browser, gli aggiornamenti di Extended Stable si applicano Microsoft Edge'applicazione Stable. Pertanto, per il client Windows Update per determinare se applicare gli aggiornamenti Stable o Extended Stable, controlla lo stato dei criteri di gruppo "Sostituzione canale di destinazione". Se il criterio non è configurato o è impostato su "Stabile", verranno applicati gli aggiornamenti stabili. Se è impostato su "Extended Stable", verranno applicati gli aggiornamenti extended stable. Segui le istruzioni precedenti per acconsentire esplicitamente a Extended Stable with Automatic Updates per istruzioni su come impostare correttamente i Criteri di gruppo. 

## <a name="flighting-pre-release-channels-in-your-organization"></a>Flighting Pre-release Channels in your Organization

I criteri di gruppo "Sostituzione canale di destinazione" possono essere utilizzati anche per eseguire il flight senza problemi dei canali non rilasciati di Microsoft Edge nell'organizzazione senza che gli utenti necessitino di utilizzare una seconda applicazione Web browser. Ad esempio, è possibile impostare il criterio "Sostituzione canale di destinazione" su "Beta" per un insieme rappresentativo di utenti dell'organizzazione. Quando questi utenti aprono Microsoft Edge, eseguono la versione del canale Beta anziché Stable (probabilmente senza nemmeno rendersene conto!). In questo modo è possibile ottenere informazioni approfondite sulle prestazioni della versione successiva di Microsoft Edge nell'organizzazione e contribuire a verificare che tutto funzioni come previsto nell'ambiente. Riceverete i primi segnali dagli utenti che riscontrano problemi e possono verificare che vengano corretti prima della pubblicazione del rilascio nel Canale Stabile. Nell'ambito della risoluzione del problema di un utente, la stringa della versione in ti informerà se il canale dell'utente è diverso dal `edge://settings/help` canale Stable predefinito.

> [!NOTE]
> Poiché i canali "Beta" e "Dev" di Microsoft Edge hanno numeri di versione principali maggiori di quelli di "Stable", se si prende un aggiornamento al canale "Beta" o "Dev" e si desidera ripristinare Stable, sarà necessaria la funzionalità di rollback di [Microsoft Edge.](/DeployEdge/edge-learnmore-rollback) Se si imposta semplicemente "Override canale di destinazione" su Stable, non si riceveranno aggiornamenti finché l'ultima versione di Stable non avrà un numero di versione maggiore rispetto alla versione di Microsoft Edge attualmente in esecuzione nel dispositivo.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Download di canali](https://aka.ms/EdgeEnterprise)
