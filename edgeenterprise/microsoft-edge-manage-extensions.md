---
title: Gestire le estensioni di Microsoft Edge nella grande impresa
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Gestire le estensioni di Microsoft Edge nella grande impresa
ms.openlocfilehash: 69c10bfa1e041d48f99594e6ac85dd39ba66379ca8d6d7fe12f1bdef6f3b54fe
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724914"
---
# <a name="manage-microsoft-edge-extensions-in-the-enterprise"></a>Gestire le estensioni di Microsoft Edge nella grande impresa

In questo articolo vengono indicate le procedure consigliate agli amministratori per gestire le estensioni di Microsoft Edge all’interno delle organizzazioni. È possibile utilizzare le informazioni contenute nell’articolo per sviluppare una strategia dedicata alla gestione delle estensioni all’interno dell'organizzazione.

> [!NOTE]
> L’articolo riguarda Microsoft Edge versione 77 o successiva.

## <a name="introduction"></a>Introduzione

Le organizzazioni desiderano proteggere i dati dell'azienda e degli utenti nonché valutare le estensioni del browser per assicurarsi che siano sicure e pertinenti per l'azienda. Gli amministratori desiderano:

- Impedire l'installazione di app ed estensioni non supportate.
- Mantenere le estensioni necessarie agli utenti per svolgere il proprio lavoro.
- Gestire l'accesso ai dati dell'azienda e degli utenti.  

Questo è il primo di una serie di articoli che intende fornire informazioni utili agli amministratori per gestire le estensioni in modo da offrire agli utenti un'esperienza sicura e produttiva. La serie di articoli riguarda diverse opzioni e consente di scegliere il metodo migliore per la gestione delle estensioni. La serie è costituita dai seguenti articoli:

- [Gestire le estensioni di Microsoft Edge nella grande impresa](microsoft-edge-manage-extensions.md). Creare una strategia per gestire le estensioni e configurare i modelli amministrativi necessari per la gestione del browser.
- [Usare i criteri di gruppo per gestire le estensioni di Microsoft Edge](microsoft-edge-manage-extensions-policies.md). Opzioni che sfruttano i criteri di gruppo per gestire le estensioni.
- [Creare un archivio Web per ospitare le estensioni di Microsoft Edge](microsoft-edge-manage-extensions-webstore.md). Creare e ospitare le estensioni.
- [Domande frequenti sulle estensioni di Microsoft Edge](microsoft-edge-manage-extensions-faq.md). Domande frequenti.

## <a name="things-to-consider-when-managing-extensions"></a>Aspetti da considerare per la gestione delle estensioni

Gli utenti devono accedere a determinate app, siti ed estensioni per svolgere il proprio lavoro proteggendo allo stesso tempo i dati dell'azienda e degli utenti. Una strategia di sicurezza efficace consiste nel porsi le domande giuste per l’azienda e chiedersi in che modo le estensioni possono soddisfare le esigenze dell'azienda. Alcune delle domande principali da porsi sono:

- Quali normative e misure di conformità è necessario rispettare?
- Alcune estensioni richiedono autorizzazioni eccessivamente ampie, che potrebbero compromettere i criteri di sicurezza dei dati dell’azienda?
- Quanti dati dell'azienda e degli utenti vengono archiviati sui dispositivi degli utenti?

Rispondendo a queste domande, è possibile utilizzare i criteri granulari di Microsoft Edge per:

- Bloccare o consentire estensioni sui computer degli utenti in base ai criteri di protezione dei dati.
- Forzare l'installazione delle estensioni sui dispositivi degli utenti in modo da fornire a questi ultimi gli strumenti necessari per rimanere produttivi.
- Richiedere una minore quantità di diritti necessari agli utenti per svolgere il proprio lavoro tramite elenchi di estensioni consentite e bloccate.

Per alcune estensioni specifiche, il modello tradizionale per la gestione delle estensioni sfrutta l'approccio degli elenchi di estensioni consentite e bloccate. Tuttavia, Microsoft Edge consente agli utenti anche di gestire le autorizzazioni richieste dalle estensioni. Tramite questo modello, è possibile decidere quali diritti e autorizzazioni sono consentite per essere utilizzate dalle estensioni sui computer e dispositivi, quindi implementare un criterio globale che consenta o blocchi le estensioni in base alle proprie esigenze.  

## <a name="understand-extension-permissions"></a>Informazioni sulle autorizzazioni delle estensioni

Per una corretta esecuzione, è possibile che le estensioni richiedano diritti per apportare modifiche su un dispositivo o una pagina Web. Tali diritti sono noti come “autorizzazioni”. Gli sviluppatori devono elencare i diritti e l’accesso richiesti dalle estensioni. Vi sono due categorie principali di autorizzazioni. Molte estensioni necessitano di entrambe le autorizzazioni seguenti:

- Autorizzazioni host, che necessitano di un’estensione per elencare le pagine Web che possono essere visualizzate o modificate.
- Autorizzazioni del dispositivo, ovvero i diritti necessari a un'estensione per essere eseguita sul dispositivo.

Alcuni esempi di queste autorizzazioni sono: accesso a una porta USB, schermata per archiviazione o visualizzazione e comunicazione con programmi nativi.  

## <a name="get-ready-to-manage-extensions"></a>Prepararsi a gestire le estensioni

## <a name="before-you-begin"></a>Prima di iniziare

Le opzioni di estensione presuppongono che si abbia già gestito Microsoft Edge per gli utenti. Per ulteriori informazioni sulla configurazione dei modelli amministrativi per i criteri di Microsoft Edge, consultare:

-   [Configurare le impostazioni dei criteri di Microsoft Edge in Windows](/DeployEdge/configure-microsoft-edge)
-   [Configurare per Windows con Intune](/mem/intune/configuration/administrative-templates-configure-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
-   [Configurare per Windows con Gestione dispositivi mobili](/deployedge/configure-edge-with-mdm)
-   [Configurare per macOS con un file plist](/deployedge/configure-microsoft-edge-on-mac)
-   [Configurare per macOS con Jamf](/deployedge/configure-microsoft-edge-on-mac-jamf)

I passaggi di configurazione descritti in questo articolo sono destinati a Windows. Per l'implementazione corrispondente in MAC/Linux, consultare la guida di riferimento per i criteri del browser Microsoft Edge.

## <a name="decide-which-extensions-to-allow"></a>Decidere quali estensioni consentire

La maggior parte delle organizzazioni deve gestire le estensioni tramite le autorizzazioni e i siti Web per cui dispone dell’accesso. Il metodo indicato è più sicuro, più semplice da gestire ed è scalabile per le organizzazioni di grandi dimensioni.  

- Autorizzazioni bloccate/concesse: consente di controllare le estensioni tramite le autorizzazioni necessarie.
- Host di runtime per blocco: consente di controllare i siti Web a cui possono accedere queste estensioni.

L'utilizzo di tale approccio consente di risparmiare tempo poiché è necessario impostare queste opzioni una sola volta. Inoltre, con il criterio Host di runtime, è possibile proteggere i siti più importanti. Sono disponibili altre opzioni, come ad esempio:

-   Forza l'installazione delle estensioni: consente di installare le estensioni automaticamente.
-   Elenco consenti/bloccati (se necessario): consente di decidere quali estensioni è consentito installare.

Utilizzare i passaggi seguenti come guida per decidere quali estensioni consentire all'interno dell'organizzazione.

1. Creare un elenco delle estensioni necessarie ai dipendenti da installare sui computer. Esaminare le estensioni in un ambiente di test per eseguire la diagnosi di eventuali problemi di compatibilità con le app interne.
2. Scegliere quali siti è necessario rendere più sicuri.

   - Individuare per quali siti Web o domini interni vulnerabili è necessario bloccare le modifiche o la lettura dei dati da parte delle estensioni.  
   - Impedire l'accesso a tali siti Web tramite il blocco delle chiamate API quando viene eseguita l'estensione. Ciò include il blocco delle richieste Web, la lettura dei cookie, JavaScript injection, XHR e così via.

3. Determinare le autorizzazioni necessarie per l'esecuzione di queste estensioni. Identificare le autorizzazioni che comportano eventuali rischi per gli utenti.

   - Controllare le estensioni installate dagli utenti e individuare le autorizzazioni necessarie. È possibile esaminare il file manifesto JSON di App Web nel codice dell'estensione. Seguire i passaggi seguenti per individuare i diritti necessari all'estensione:

     - Installare l'estensione dal sito Web [Componenti aggiuntivi di Microsoft Edge](https://microsoftedge.microsoft.com/addons/) o dal [Chrome Web Store](https://chrome.google.com/webstore).
     - Testare l'estensione e comprendere la modalità di funzionamento all’interno dell'organizzazione.
     - Rivedere le autorizzazioni richieste dall'estensione passando a *edge://extensions*. Ad esempio, l'estensione di Microsoft Office visualizzata nella schermata successiva richiede le autorizzazioni "Leggi la cronologia esplorazioni" e "Visualizza notifiche". Valutare l'utilità dell’estensione rispetto al livello di autorizzazioni richieste. Dopo aver approvato un'estensione per l'organizzazione, gestirla utilizzando gli strumenti seguenti.
   :::image type="content" source="media/microsoft-edge-manage-extensions/manage-extesions-office-extension.png" alt-text="Estensione di Microsoft Office con autorizzazioni.":::

   - È inoltre possibile convalidare le estensioni necessarie agli utenti prima di approvarle all’interno dell'organizzazione. È possibile che alcune delle autorizzazioni utilizzate dalle estensioni siano generiche. Per le app di rilevanza per l’azienda, è possibile contattare direttamente lo sviluppatore o il fornitore dell'app per ottenere ulteriori informazioni sull'estensione o esaminare il codice sorgente. Questi ultimi dovrebbero essere in grado di descrivere in dettaglio le modifiche che l'estensione può apportare a dispositivi e siti Web.
   - Rivedere l'elenco Dichiara autorizzazioni in cui sono elencate tutte le autorizzazioni che un'estensione può utilizzare. Consultando questo elenco, è possibile decidere quali autorizzazioni si desidera consentire all'interno dell'organizzazione.

4. Creare un elenco principale a partire dai dati raccolti. Questo elenco includerà le informazioni seguenti:

   - **Estensioni necessarie**. È possibile organizzare l’elenco a seconda del reparto, della sede dell'ufficio o di altre informazioni rilevanti.
   - **Elenco estensioni consentite**. Estensioni necessarie con autorizzazioni, che possono essere bloccate ma che è possibile eseguire. Tali estensioni sono necessarie agli utenti o non comportano rischi legati alle conversazioni con il fornitore.
   - **Elenco estensioni bloccate**. Estensioni la cui l'installazione è bloccata. Le estensioni contenute in questo elenco non dispongono delle autorizzazioni necessarie per essere eseguite. Includere anche i siti e i domini principali da mantenere sicuri e per i quali le estensioni non dispongono dell’accesso. In seguito è possibile confrontare l’elenco di estensioni bloccate con le altre implementate. Potreste scoprire che è possibile rivedere i criteri dell’attuale elenco di estensioni bloccate.

5. Presentare l'elenco alle parti interessate e al team IT per ottenere il loro consenso.
6. Esaminare i nuovi criteri nel lab o tramite un piccolo progetto pilota all’interno dell'organizzazione.
7. Implementare i nuovi set di criteri per i dipendenti attraverso più fasi. Per ulteriori informazioni, consultare [Usare i criteri di gruppo per gestire le estensioni di Microsoft Edge](microsoft-edge-manage-extensions-policies.md).
8. Esaminare il feedback degli utenti.
9. Ripetere e ottimizzare il processo mensilmente, trimestrale o annualmente.

Applicando la baseline di autorizzazioni consentite e proteggendo i siti dell'azienda vulnerabili, è possibile fornire all'azienda maggiore sicurezza, offrendo al contempo un'esperienza migliore per gli utenti. Il personale potrebbe installare estensioni non consentite prima, ma senza poterle eseguire sui siti aziendali vulnerabili.  

## <a name="see-also"></a>Consultare anche

- [Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge](microsoft-edge-manage-extensions-policies.md)
- [Creare un archivio Web per ospitare le estensioni di Microsoft Edge](microsoft-edge-manage-extensions-webstore.md)
- [Guida di riferimento per i criteri ExtensionSettings](microsoft-edge-manage-extensions-ref-guide.md)
- [Domande frequenti sulle estensioni di Microsoft Edge](microsoft-edge-manage-extensions-faq.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)