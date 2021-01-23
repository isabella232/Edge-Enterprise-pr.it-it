---
title: 'Gestione elenco siti dell’organizzazione in Microsoft Edge '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 01/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Abilitare e usare Enterprise Site List Manager in Microsoft Edge '
ms.openlocfilehash: 2d10886624918c97933a841c428ea66ccf5b34c9
ms.sourcegitcommit: a6c58b19976c194299be217c58b9a99b48756fd0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11281050"
---
# Gestione elenco siti dell’organizzazione in Microsoft Edge

Questo articolo spiega come abilitare l'accesso e usare Enterprise Site List Manager in Microsoft Edge per creare, modificare ed esportare il tuo l'elenco siti modalità Enterprise per la modalità Internet Explorer.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 89 o successiva.

## Panoramica

Enterprise Site List Manager è una versione in-browser dello [strumento standalone Enterprise Mode Site List Manager](https://www.microsoft.com/download/details.aspx?id=49974) che ti permette di creare, modificare ed esportare l'elenco dei siti della tua organizzazione.

I futuri miglioramenti apportati allo strumento per Internet Explorer saranno disponibili attraverso Enterprise Site List Manager in Microsoft Edge. Lo strumento standalone continuerà a essere disponibile nell'Area download, ma non riceverà aggiornamenti delle caratteristiche.

## Abilitazione dell'accesso a Enterprise Site List Manager

È possibile configurare l'accesso allo strumento usando il criterio di gruppo [EnterpriseModeSiteListAllowedallowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed).

Se abilitata, gli utenti visualizzano un'opzione denominata Enterprise Site List Manager nel riquadro di spostamento sinistro in *edge://compat*. Se disabilitato, gli utenti non vedono il punto di ingresso di Enterprise Site List Manager nel riquadro di spostamento sinistro. Questo è il comportamento predefinito.

## Uso di Enterprise Mode Site List Manager

Lo strumento Enterprise Site List Manager usa la versione 2 dello schema. Se importi uno schema della versione v.1 in Enterprise Mode Site List Manager (schema v.2), il codice XML viene salvato nella versione v.2 dello schema.

### Aggiungere singoli siti all'elenco dei siti  

Usa la procedura seguente per aggiungere singoli siti all'elenco dei siti.

> [!NOTE]
> Puoi aggiungere solo URL specifici, non aree Intranet o Internet.

1. In Enterprise Site List Manager, fare clic su  **Aggiungi sito**.
2. Digitare l'URL del sito Web che si desidera aggiungere, ad esempio <domain>.com o <domain>.com/<path>  nella casella dell'URL.
3. Selezionare una delle opzioni seguenti dall'elenco **Apri in** :

   - **IE11**. Apre il sito nell'applicazione IE11.
   - **modalità IE**. Apre il sito in modalità Internet Explorer su Microsoft Edge, se abilitato e nell'app Internet Explorer 11 in caso contrario. Vedi  [Modalità Internet Explorer su Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode).
   - **MSEdge**. Apre il sito su Microsoft Edge.
   - **Configurabile**. Consente al sito di partecipare alla determinazione del motore in modalità Internet Explorer. Vedi [Siti configurabili in modalità IE](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
   - **Nessuno**. Si apre in qualsiasi browser scelto dall'utente.  

4. In  **Modalità compatibilità**, scegli una delle opzioni seguenti:

   - **IE8Enterprise**. Carica il sito nella modalità Enterprise di IE8.
   - **IE7Enterprise**. Carica il sito nella modalità Enterprise di IE7.
   - **IE\**. Dove [x] è il numero di modalità documento e il sito viene caricato nella modalità documento specificata.
   - **Modalità predefinita**. Carica il sito usando la modalità di compatibilità predefinita per la pagina.

   Il percorso all'interno di un dominio può richiedere una modalità di compatibilità diversa rispetto al dominio stesso. Ad esempio, il dominio potrebbe essere visualizzato correttamente nel browser Internet Explorer 11 predefinito, ma il percorso potrebbe presentare problemi e richiedere l'uso della modalità Enterprise. Se hai aggiunto il dominio in precedenza, la tua scelta originale per la compatibilità sarà ancora selezionata. Se invece il dominio è nuovo, viene automaticamente selezionata la  **modalità Enterprise di IE8** .

   La modalità Enterprise ha la precedenza sulle modalità documento. In questo modo i siti che sono già inclusi nell'elenco dei siti per la modalità Enterprise non saranno interessati da questo aggiornamento e continueranno a essere caricati in modalità Enterprise, come di consueto. Per informazioni dettagliata sull'uso delle modalità documento, vedi  [Risolvere i problemi di compatibilità Web con le modalità documento e l'elenco dei siti per la modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list).

5. La casella di controllo **Allow Redirect** si applica al trattamento dei reindirizzamenti lato server. Se selezioni questa casella, i reindirizzamenti lato server si apriranno nel browser specificato dal tag open-in. Per altre informazioni, vedi  [qui](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes).
6. Scrivi qualsiasi commento sul sito web nella casella  **Commenti**. Gli amministratori possono vedere i commenti solo mentre sono in questo strumento e questi commenti vengono mantenuti nel file XML dell'elenco dei siti.
7. Fai clic su  **Aggiungi** per aggiungere il sito all'elenco dei siti.

### Esportare l'elenco dei siti in XML

Dopo avere creato l'elenco dei siti in Enterprise Mode Site List Manager, puoi esportare il contenuto in un file XML o uno di Modalità Enterprise (con estensione EMIE). 

> [!NOTE]
> Questo file include tutti gli URL, incluse le selezioni per la modalità di compatibilità, e deve essere archiviato in una posizione sicura.

Per esportare l'elenco dei siti, segui questi passaggi:

1. In Enterprise Site List Manager, fai clic su **Esporta in formato XML**.
2. Immetti un **Numero versione** e un **Nome file**.
3. Fare clic su **Esporta**.

Puoi salvare il file in locale o in una condivisione di rete. Devi comunque assicurarti di distribuirlo nella posizione specificata nella chiave del Registro di sistema. Per altre informazioni, vedi  [Attivare la modalità Internet Explorer e usare un elenco di siti](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).

### Importare più siti nell'elenco dei siti

Dopo aver creato il file con estensione xml, puoi aggiungere in blocco i siti all'editor attraverso **Importa da XML**.

Per sostituire tutto il contenuto dell'editor, fai clic sui tre punti (...) e scegli **Deselezionare elenco**. Dopo avere deselezionato l'editor, usa i passaggi successivi per importare il sito.

1. In Enterprise Site List Manager, fai clic su **Importa da XML**. 
2. Fai clic su **Scegli file** per selezionare l'elenco dei siti per aggiungere i siti inclusi allo strumento. Seleziona l'elenco dei siti che vuoi aggiungere e fai clic su  **Apri**. I formati supportati per l'importazione sono xml, emie o txt contenenti lo schema versione 2 per l'elenco dei siti in modalità Enterprise. Vedi le [Indicazioni per lo schema versione 2 della modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).
3. Fai clic su  **Carica** per aggiungere i siti dal file all’editor.

Puoi salvare il file in locale o in una condivisione di rete. Devi comunque assicurarti di distribuirlo nella posizione specificata nella chiave del Registro di sistema. Per altre informazioni, vedi  [Attivare la modalità Internet Explorer e usare un elenco di siti](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).

### Modificare siti nell'elenco dei siti

 È possibile modificare gli attributi delle voci del sito esistenti su Enterprise Site List Manager. Puoi anche aggiungere, rimuovere o eliminare commenti associati.

1. In Enterprise Site List Manager, fai clic sui tre punti (...) e scegli **Modifica sito** per l'URL da modificare.
2. Puoi modificare qualsiasi attributo della voce del sito tranne l'URL. Fai clic su **Salva** dopo aver completato le modifiche.

   > [!NOTE]
   > Se vuoi eliminare una voce del sito, scegli **Elimina sito** al passaggio 1.

3. Fai clic su **Esporta in XML** e salva il file aggiornato.

Puoi salvare il file in locale o in una condivisione di rete. Devi comunque assicurarti di distribuirlo nella posizione specificata nella chiave del Registro di sistema. Per altre informazioni, vedi  [Attivare la modalità Internet Explorer e usare un elenco di siti](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).

### Visualizzare l'anteprima dell'elenco dei siti in formato XML

Puoi visualizzare l'anteprima dei siti nell'editor in formato XML prima di esportare e salvare nel percorso dell'elenco dei siti. Fai clic su l **'anteprima XML** per aprire il file in una nuova scheda.

### Eseguire ricerche in Enterprise Site List Manager

Puoi eseguire una ricerca per determinare se uno specifico sito è già inserito nell'elenco di siti, in modo da evitare di aggiungerlo nuovamente.

Per eseguire una ricerca, digita parte dell'URL nella casella di ricerca  **Filtra siti per URL** nell'angolo in alto a destra dell'editor.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [Informazioni aggiuntive sulla modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Informazioni aggiuntive sulla funzionalità di individuazione siti aziendale](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)
