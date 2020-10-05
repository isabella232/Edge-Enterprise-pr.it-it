---
title: Microsoft Edge e Microsoft Defender Application Guard
ms.author: srugh
author: dan-wesley
manager: seanlyn
ms.date: 10/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Supporto di Microsoft Edge per Microsoft Defender Application Guard
ms.openlocfilehash: 7052c8cee9282c0ca2f5cafaa608e7e4e71d111d
ms.sourcegitcommit: 3478cfcf2b03944213a7c7c61f05490bc37aa7c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "11094760"
---
# Supporto di Microsoft Edge per Microsoft Defender Application Guard

Questo articolo descrive come Microsoft Edge supporta Microsoft Defender Application Guard (Application Guard).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## Panoramica

Gli architetti della sicurezza nell'organizzazione devono gestire la tensione esistente tra produttività e sicurezza. È relativamente facile bloccare un browser e consentire solo il caricamento di pochi siti attendibili. Questo approccio migliorerà le condizioni di sicurezza complessive, ma è verosimilmente meno produttivo. Rendendolo meno restrittivo al fine di migliorare la produttività, si aumenta il profilo di rischio. Si tratta di un equilibrio difficile da trovare.

È ancora più difficile stare al passo con le nuove minacce emergenti in questo scenario di minaccia in continuo cambiamento. I browser restano la superficie di attacco principale nei dispositivi client, perché la loro attività di base è quella di consentire agli utenti di accedere, scaricare e aprire contenuto non attendibile da origini non attendibili. Gli autori di minacce sono costantemente al lavoro per creare nuove forme di ingegneria sociale al fine di attaccare il browser. La prevenzione degli incidenti di sicurezza o le strategie di rilevamento/risposta non possono garantire la sicurezza al 100%.

Una delle principali strategie di sicurezza da considerare è la [Assume Breach Methodology](https://docs.microsoft.com/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology), ossia la metodologia di presunzione di violazione, che implica l'accettazione della riuscita di un attacco almeno una volta nonostante gli sforzi per impedirlo. Questo presupposto richiede la creazione di difese che contengano il danno, in modo che la rete aziendale e altre risorse rimangano protette in questo scenario.  La distribuzione di Application Guard per Microsoft Edge si adatta perfettamente a questa strategia.

## Informazioni su Application Guard

Progettato per Windows 10 e Microsoft Edge, Application Guard usa un approccio di isolamento hardware, che consente di avviare gli spostamenti nei siti non attendibili all'interno di un contenitore. L'isolamento hardware consente alle organizzazioni di proteggere la rete e i dati aziendali nel caso in cui gli utenti visitino un sito che è compromesso o dannoso.

L'amministratore dell'organizzazione definisce quali sono i siti, le risorse del cloud e le reti interne attendibili. Tutto ciò che non è incluso nell'elenco dei siti attendibili viene considerato non attendibile. Questi siti sono isolati dalla rete e dai dati aziendali nel dispositivo dell'utente.

Per altre informazioni, vedere [Che cos'è Application Guard e come funziona?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work).

Lo screenshot seguente mostra un esempio di messaggio di Application Guard che indica che l'utente sta navigando in uno spazio sicuro.

![Messaggio di esplorazione sicura di Application Guard](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## Novità

Il supporto per Application Guard nel nuovo browser Microsoft Edge ha pari funzionalità con la versione legacy di Microsoft Edge e include diversi miglioramenti.

### Supporto dell'estensione all'interno del contenitore

Il supporto per l'estensione all'interno del contenitore è una delle principali richieste dei clienti. Gli scenari sono diversi, da quelli che vogliono eseguire il blocco di annunci all'interno del contenitore per aumentare le prestazioni del browser per poter eseguire estensioni personalizzate nel contenitore.

Sono ora supportate le installazioni di estensione nel contenitore, a partire da Microsoft Edge versione 81. Il supporto può essere controllato tramite criterio. Le `updateURL` usate nel criterio di [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) devono essere aggiunte come Risorse neutre ai criteri di Isolamento della rete usati da Application Guard.

Alcuni esempi di supporto contenitore includono gli scenari seguenti:

- Forzare le installazioni di un'estensione nell'host
- Rimozione di un'estensione dall'host
- Estensioni bloccate nell'host

> [!NOTE]
> È anche possibile installare manualmente singole estensioni all'interno del contenitore dall'archivio estensioni. Le estensioni installate manualmente verranno conservate nel contenitore solo se è abilitato il criterio [Consenti il salvataggio permanente](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings).

### Identificazione traffico Application Guard via proxy doppio

Alcuni clienti aziendali stanno distribuendo Application Guard con un caso specifico di utilizzo in cui è necessario identificare il traffico Web in uscita da un contenitore Microsoft Defender Application Guard a livello di proxy. A partire da Stable Channel versione 84, Microsoft Edge supporterà il doppio proxy per soddisfare questo requisito. Questa funzionalità può essere configurata usando i criteri di [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy).

Il disegno seguente mostra la doppia architettura proxy per Microsoft Edge.

![Doppia architettura proxy per Application Guard](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### Pagina di diagnostica per la risoluzione dei problemi

Un altro aspetto che desta maggiori preoccupazioni per l'utente è la risoluzione dei problemi relativi alla configurazione di Application Guard in un dispositivo quando viene segnalato un problema. Microsoft Edge include una pagina di diagnostica (`edge://application-guard-internals`) per risolvere i problemi degli utenti. Una di queste diagnostiche riesce a controllare l'URL trust in base alla configurazione nel dispositivo dell'utente.

Lo screenshot seguente mostra una pagina di diagnostica con più schede che consente di diagnosticare i problemi segnalati dall'utente nel dispositivo.

![Pagina di diagnostica di Application Guard](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### Aggiornamenti di Microsoft Edge nel contenitore

Gli aggiornamenti della versione legacy di Microsoft Edge nel contenitore fanno parte del ciclo di aggiornamento del sistema operativo Windows. Dato che la nuova versione di Microsoft Edge si aggiorna indipendentemente dal sistema operativo Windows, non esiste più la dipendenza dagli aggiornamenti del contenitore. Il canale e la versione dell'host Microsoft Edge vengono replicati all'interno del contenitore.

## Prerequisiti

I requisiti seguenti si applicano ai dispositivi che usano Application Guard con Microsoft Edge:

- Windows 10 1809 (RS5) e versioni successive.
- Solo SKU dei client Windows.

  > [!NOTE]
  > Application Guard è supportato solo nelle SKU di Windows 10 Pro e Windows 10 Enterprise.

- Una delle soluzioni di gestione descritte nei [Requisiti software](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)

## Come installare Application Guard

Gli articoli seguenti forniscono le informazioni necessarie per installare, configurare e testare Application Guard con Microsoft Edge.

- [Requisiti di sistema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [Installare Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [Configurare le impostazioni di criteri di gruppo di Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [Testare Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## Domande frequenti

### Application Guard funziona in modalità IE?

La modalità IE supporta la funzionalità di Application Guard, ma non è previsto l'uso di questa caratteristica in modalità IE. Per un elenco di siti interni attendibili è consigliabile usare la modalità IE, mentre Application Guard può essere usato solo per i siti non attendibili. Assicurarsi che tutti i siti in modalità IE o gli indirizzi IP vengano aggiunti anche ai criteri di Isolamento della rete per essere considerati come risorsa attendibile da Application Guard.

### È necessario installare l'estensione Application Guard per Chrome?

No, la funzionalità Application Guard è supportata in modo nativo in Microsoft Edge. In effetti, l'estensione Application Guard per Chrome non è una configurazione supportata in Microsoft Edge.

### Ci sono altre domande frequenti relative alla piattaforma?

Sì. [Domande frequenti: Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
