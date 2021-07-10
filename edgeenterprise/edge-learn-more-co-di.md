---
title: ClickOnce e DirectInvoke in Microsoft Edge
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Informazioni su ClickOnce e DirectInvoke in Microsoft Edge.
ms.openlocfilehash: 3d124f141e9212ba5ab25d4b725d32add62077a3
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642052"
---
# <a name="understand-the-clickonce-and-directinvoke-features-in-microsoft-edge"></a>Informazioni sulle funzionalità ClickOnce e DirectInvoke in Microsoft Edge

ClickOnce e DirectInvoke sono funzionalità disponibili in Internet Explorer e Microsoft Edge (versione 45 e precedenti) che supportano l'uso di un gestore di file per scaricare i file da un sito Web. Anche se servono a scopi diversi, entrambe le funzionalità consentono ai siti Web di specificare che un file richiesto per il download viene passato a un gestore di file nel dispositivo dell'utente. Le richieste ClickOnce vengono gestite dal gestore di file nativo in Windows. Le richieste DirectInvoke vengono gestite da un gestore di file registrato specificato dal sito Web che ospita il file.

Per altre informazioni su queste funzionalità, vedi:

- [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [DirectInvoke]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> Attualmente, Chromium non fornisce il supporto nativo per ClickOnce o DirectInvoke.

## <a name="overview-prerequisites-and-process"></a>Panoramica: prerequisiti e processo

Affinché ClickOnce e DirectInvoke funzionino nel modo per cui sono state progettate e le richieste arrivino in modo corretto al gestore di file, quest'ultimo deve essere registrato nel sistema operativo in modo che supporti ClickOnce o DirectInvoke. Questa registrazione si verifica in genere quando viene installato il sistema operativo originale o quando un nuovo programma installato richiede la possibilità di usare DirectInvoke per gli aggiornamenti.

Quando un sito Web riceve una richiesta di download che richiede ClickOnce o DirectInvoke, si verificano le azioni seguenti:

- Il sito Web richiede che il browser usi un gestore di file specificato.
- Il browser controlla il Registro di sistema del sistema operativo per verificare se il gestore di file è registrato per il tipo di file richiesto.
- Se il gestore di file è registrato, il browser lo chiama e gli passa l'URL come argomento.
- Il gestore di file elabora l'URL e scarica il file.

  > [!NOTE]
  > L'URL viene usato per determinare l'origine del file, nonché i parametri da usare per l'accesso al file.  Ad esempio: endpoint, un manifesto oppure metadati.

## <a name="use-cases"></a>Casi d'uso

I seguenti casi d'uso sono rappresentativi.

Puoi usare ClickOnce per distribuire e aggiornare facilmente il software nei dispositivi con un'interazione utente minima. Gli utenti possono installare ed eseguire un'applicazione Windows facendo clic su un collegamento in una pagina Web. Se configurata correttamente, l'applicazione ClickOnce può installare programmi senza che gli utenti impostino le configurazioni per il programma di installazione. Sono inclusi i percorsi dei file, le opzioni da installare e così via.

I casi d'uso di DirectInvoke dipendono dalla finalità del sito Web che richiede DirectInvoke. Ad esempio, la funzionalità di modifica dei file in collaborazione di Microsoft Word. Invece di fare clic su un collegamento e scaricare l'intera copia di un documento a cui si sta lavorando con i colleghi, DirectInvoke consente di scaricare le parti del documento che sono state modificate. Questa strategia riduce la quantità di dati trasferiti e si può ridurre il tempo necessario per aprire il documento.  

## <a name="current-support-for-clickonce-and-directinvoke-in-microsoft-edge"></a>Supporto corrente per ClickOnce e DirectInvoke in Microsoft Edge

Supporto per ClickOnce e DirectInvoke:

- ClickOnce e DirectInvoke sono supportati per impostazione predefinita per tutti gli utenti di Windows.

  > [!NOTE]
  > Gli utenti che vogliono disabilitare il supporto per ClickOnce possono andare su *edge://flags/#edge-click-once* e selezionare **Disabilita** nell'elenco a discesa. Fai clic su **Riavvia** per riavviare il browser.

- ClickOnce e DirectInvoke non sono supportate in nessuna piattaforma diversa da Windows.

## <a name="clickonce-and-directinvoke-file-handling-security"></a>Sicurezza per la gestione dei file con ClickOnce e DirectInvoke

ClickOnce e DirectInvoke sono funzioni protette dal servizio di analisi della reputazione URL di Microsoft Defender SmartScreen.

Se una richiesta ClickOnce o DirectInvoke è contrassegnata dal servizio di reputazione URL di Microsoft Defender SmartScreen come non sicura, agli utenti per cui ClickOnce o DirectInvoke è abilitata vengono visualizzate due finestre popup.

Nella prima finestra viene chiesto all'utente se vuole aprire il file. Questa finestra viene visualizzata indipendentemente dal fatto che il file sia stato contrassegnato come sicuro o non sicuro. L'utente può selezionare i campi **Segnala file come non sicuro**, **Annulla** per annullare la richiesta o fare clic su **Apri** per continuare.

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

Se l'utente tenta di aprire il file e il file è stato contrassegnato come non sicuro, viene visualizzata una seconda finestra popup.  In tale finestra si avvisa l'utente che il file è stato contrassegnato come non sicuro e si chiede se desidera scaricare il file.

La seconda finestra popup viene visualizzata solo se:

- il file è un file ClickOnce o DirectInvoke
- ClickOnce o DirectInvoke sono abilitate
- il file è contrassegnato come non sicuro

 ![Prompt per aprire un file non sicuro](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> Se ClickOnce o DirectInvoke sono disabilitate, i file richiesti vengono considerati come download regolari e, se contrassegnati come non sicuri, verranno considerati tali. Questo è coerente con il trattamento di altri download non sicuri.

## <a name="clickonce-and-directinvoke-policies"></a>Criteri di ClickOnce e DirectInvoke

Esistono due criteri di gruppo che è possibile usare per abilitare o disabilitare ClickOnce e DirectInvoke per gli utenti aziendali. I due criteri sono [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled) e [DirectInvokeEnabled](./microsoft-edge-policies.md#directinvokeenabled). Questi due criteri sono contrassegnati nell'Editor Criteri di gruppo come "Consenti agli utenti di aprire file con il protocollo ClickOnce" e "Consenti agli utenti di aprire i file usando il protocollo DirectInvoke".

## <a name="clickonce-and-directinvoke-behavior"></a>Comportamento di ClickOnce e DirectInvoke

Gli esempi seguenti mostrano la gestione dei file quando ClickOnce e DirectInvoke sono abilitate o disabilitate.

### <a name="clickonce-enabled"></a>ClickOnce abilitata

1. Un utente apre un collegamento a una pagina che richiede il supporto di ClickOnce e riceve il prompt visualizzato nella schermata successiva.

   ![Prompt per aprire un file non sicuro](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. Dopo che l'utente fa clic su **Apri**, ClickOnce tenta di avviare l'applicazione.

   ![ClickOnce tenta di avviare l'applicazione](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. Dopo che l'utente fa clic su **Apri**, nel browser viene visualizzata una finestra popup che chiede all'utente se è sicuro di installare l'applicazione.

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > L'interfaccia, la messaggistica e le opzioni visualizzate dal gestore di file ClickOnce variano a seconda del tipo e della configurazione del file a cui si accede.

### <a name="clickonce-disabled"></a>ClickOnce disabilitata

1. Quando un utente apre un collegamento a una pagina che richiede il supporto di ClickOnce, viene visualizzato un messaggio nell'area di download simile a quello nella schermata successiva.

   ![Prompt per il download del file](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### <a name="directinvoke-enabled"></a>DirectInvoke abilitata

1. Un utente apre un collegamento a una pagina che richiede il supporto di DirectInvoke e riceve il prompt visualizzato nella schermata successiva.

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. Quando l'utente fa clic su **Apri**, viene aperto il gestore di file richiesto. In questo esempio Microsoft Word viene usato per aprire il documento visualizzato nella schermata precedente.

   > [!NOTE]
   > L'interfaccia, la messaggistica e le opzioni visualizzate dal gestore di file DirectInvoke variano a seconda del tipo e della configurazione del file a cui si accede.

### <a name="directinvoke-disabled"></a>DirectInvoke disabilitata

1. Quando un utente apre un collegamento a una pagina che richiede il supporto di DirectInvoke, DirectInvoke si comporta in modo analogo a quando ClickOnce è disabilitata. Verrà visualizzato un messaggio nell'area di download simile a quello nella schermata successiva.

   ![Prompt per aprire il file](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## <a name="see-also"></a>Vedi anche

- [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [DirectInvoke in Internet Explorer](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/jj215788(v=vs.85))
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)