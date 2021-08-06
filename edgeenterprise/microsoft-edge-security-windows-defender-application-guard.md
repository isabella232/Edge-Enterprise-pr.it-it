---
title: Microsoft Edge e Microsoft Defender Application Guard
ms.author: srugh
author: AndreaLBarr
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Supporto di Microsoft Edge per Microsoft Defender Application Guard
ms.openlocfilehash: 4bb8f48bd5ccdfd555d44cecc8cfe9253a6ba17e42f60e2b8a0086411c10e9fb
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11727024"
---
# <a name="microsoft-edge-support-for-microsoft-defender-application-guard"></a>Supporto di Microsoft Edge per Microsoft Defender Application Guard

Questo articolo descrive come Microsoft Edge supporta Microsoft Defender Application Guard (Application Guard).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="overview"></a>Panoramica

Gli architetti della sicurezza nell'organizzazione devono gestire la tensione esistente tra produttività e sicurezza. È relativamente facile bloccare un browser e consentire solo il caricamento di pochi siti attendibili. Questo approccio migliorerà le condizioni di sicurezza complessive, ma è verosimilmente meno produttivo. Rendendolo meno restrittivo al fine di migliorare la produttività, si aumenta il profilo di rischio. Si tratta di un equilibrio difficile da trovare.

È ancora più difficile stare al passo con le nuove minacce emergenti in questo scenario di minaccia in continuo cambiamento. I browser restano la superficie di attacco principale nei dispositivi client, perché la loro attività di base è quella di consentire agli utenti di accedere, scaricare e aprire contenuto non attendibile da origini non attendibili. Gli autori di minacce sono costantemente al lavoro per creare nuove forme di ingegneria sociale al fine di attaccare il browser. La prevenzione degli incidenti di sicurezza o le strategie di rilevamento/risposta non possono garantire la sicurezza al 100%.

Una delle principali strategie di sicurezza da considerare è la [Assume Breach Methodology](/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology), ossia la metodologia di presunzione di violazione, che implica l'accettazione della riuscita di un attacco almeno una volta nonostante gli sforzi per impedirlo. Questo presupposto richiede la creazione di difese che contengano il danno, in modo che la rete aziendale e altre risorse rimangano protette in questo scenario.  La distribuzione di Application Guard per Microsoft Edge si adatta perfettamente a questa strategia.

## <a name="about-application-guard"></a>Informazioni su Application Guard

Progettato per Windows 10 e Microsoft Edge, Application Guard usa un approccio di isolamento hardware, che consente di avviare gli spostamenti nei siti non attendibili all'interno di un contenitore. L'isolamento hardware consente alle organizzazioni di proteggere la rete e i dati aziendali nel caso in cui gli utenti visitino un sito che è compromesso o dannoso.

L'amministratore dell'organizzazione definisce quali sono i siti, le risorse del cloud e le reti interne attendibili. Tutto ciò che non è incluso nell'elenco dei siti attendibili viene considerato non attendibile. Questi siti sono isolati dalla rete e dai dati aziendali nel dispositivo dell'utente.

Per ulteriori informazioni:

- guardare il video sull' [isolamento del browser Microsoft Edge con Application Guard](microsoft-edge-video-security-application-guard.md)
- leggere [cos'è Application Guard e come funziona?](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)

Lo screenshot seguente mostra un esempio di messaggio di Application Guard che indica che l'utente sta navigando in uno spazio sicuro.

![Messaggio di esplorazione sicura di Application Guard](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## <a name="whats-new"></a>Novità

Il supporto per Application Guard nel nuovo browser Microsoft Edge ha pari funzionalità con la versione legacy di Microsoft Edge e include diversi miglioramenti.

### <a name="favorites-synchronizing-from-the-host-to-the-container"></a>Sincronizzazione dei Preferiti dall'host al contenitore

Alcuni clienti hanno chiesto la sincronizzazione dei Preferiti tra il browser host e il contenitore in Application Guard. A partire da Microsoft Edge 91, gli utenti hanno ora la possibilità di configurare Application Guard in modo da sincronizzare i Preferiti dall'host al contenitore. Questo assicura che anche i nuovi Preferiti vengano visualizzati nel contenitore.

Il supporto può essere controllato tramite criterio. È possibile aggiornare il criterio di Microsoft Edge [ApplicationGuardFavoritesSyncEnabled](/deployedge/microsoft-edge-policies#applicationguardfavoritessyncenabled) per abilitare o disabilitare la sincronizzazione dei Preferiti.

> [!Note]
> Per motivi di sicurezza, la sincronizzazione dei Preferiti è possibile solo dall'host al contenitore e non viceversa. Per garantire un elenco unificato dei Preferiti nell'host e nel contenitore, è stata disabilitata la gestione dei Preferiti all'interno del contenitore.

### <a name="identify-network-traffic-originating-from-the-container"></a>Identificazione del traffico di rete proveniente dal contenitore

Diversi clienti usano WDAG in una configurazione specifica in cui desiderano identificare il traffico di rete proveniente dal contenitore. Di seguito sono riportati alcuni degli scenari in cui questo può essere utile:

- Per limitare l'accesso solo a pochi siti non attendibili
- Per consentire l'accesso a Internet solo dal contenitore

A partire da Microsoft Edge versione 91, è disponibile il supporto integrato per contrassegnare il traffico di rete proveniente dai contenitori Application Guard. Questo consente alle aziende di usare un proxy per filtrare il traffico e applicare criteri specifici. È possibile usare l'intestazione per identificare il traffico che proviene dal contenitore o dall'host usando [ApplicationGuardTrafficIdentificationEnabled](/deployedge/microsoft-edge-policies#applicationguardtrafficidentificationenabled).

### <a name="extension-support-inside-the-container"></a>Supporto dell'estensione all'interno del contenitore

Il supporto per l'estensione all'interno del contenitore è una delle principali richieste dei clienti. Gli scenari sono diversi, da quelli che vogliono eseguire il blocco di annunci all'interno del contenitore per aumentare le prestazioni del browser per poter eseguire estensioni personalizzate nel contenitore.

Sono ora supportate le installazioni di estensione nel contenitore, a partire da Microsoft Edge versione 81. Il supporto può essere controllato tramite criterio. Le `updateURL` usate nel criterio di [ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist) devono essere aggiunte come Risorse neutre ai criteri di Isolamento della rete usati da Application Guard.

Alcuni esempi di supporto contenitore includono gli scenari seguenti:

- Forzare le installazioni di un'estensione nell'host
- Rimozione di un'estensione dall'host
- Estensioni bloccate nell'host

> [!NOTE]
> È anche possibile installare manualmente singole estensioni all'interno del contenitore dall'archivio estensioni. Le estensioni installate manualmente verranno conservate nel contenitore solo se è abilitato il criterio [Consenti il salvataggio permanente](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings).

### <a name="identifying-application-guard-traffic-via-dual-proxy"></a>Identificazione traffico Application Guard via proxy doppio

Alcuni clienti aziendali stanno distribuendo Application Guard con un caso specifico di utilizzo in cui è necessario identificare il traffico Web in uscita da un contenitore Microsoft Defender Application Guard a livello di proxy. A partire da Stable Channel versione 84, Microsoft Edge supporterà il doppio proxy per soddisfare questo requisito. Questa funzionalità può essere configurata usando i criteri di [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy).

Il disegno seguente mostra la doppia architettura proxy per Microsoft Edge.

![Doppia architettura proxy per Application Guard](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### <a name="diagnostic-page-for-troubleshooting"></a>Pagina di diagnostica per la risoluzione dei problemi

Un altro aspetto che desta maggiori preoccupazioni per l'utente è la risoluzione dei problemi relativi alla configurazione di Application Guard in un dispositivo quando viene segnalato un problema. Microsoft Edge include una pagina di diagnostica (`edge://application-guard-internals`) per risolvere i problemi degli utenti. Una di queste diagnostiche riesce a controllare l'URL trust in base alla configurazione nel dispositivo dell'utente.

Lo screenshot seguente mostra una pagina di diagnostica con più schede che consente di diagnosticare i problemi segnalati dall'utente nel dispositivo.

![Pagina di diagnostica di Application Guard](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### <a name="microsoft-edge-updates-in-the-container"></a>Aggiornamenti di Microsoft Edge nel contenitore

Gli aggiornamenti della versione legacy di Microsoft Edge nel contenitore fanno parte del ciclo di aggiornamento del sistema operativo Windows. Dato che la nuova versione di Microsoft Edge si aggiorna indipendentemente dal sistema operativo Windows, non esiste più la dipendenza dagli aggiornamenti del contenitore. Il canale e la versione dell'host Microsoft Edge vengono replicati all'interno del contenitore.

## <a name="prerequisites"></a>Prerequisiti

I requisiti seguenti si applicano ai dispositivi che usano Application Guard con Microsoft Edge:

- Windows 10 1809 (RS5) e versioni successive.
- Solo SKU dei client Windows.

  > [!NOTE]
  > Application Guard è supportato solo nelle SKU di Windows 10 Pro e Windows 10 Enterprise.

- Una delle soluzioni di gestione descritte nei [Requisiti software](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)

## <a name="how-to-install-application-guard"></a>Come installare Application Guard

Gli articoli seguenti forniscono le informazioni necessarie per installare, configurare e testare Application Guard con Microsoft Edge.

- [Requisiti di sistema](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [Installare Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [Configurare le impostazioni di criteri di gruppo di Microsoft Defender](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [Testare Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="does-application-guard-work-in-ie-mode"></a>Application Guard funziona in modalità IE?

La modalità IE supporta la funzionalità Application Guard, ma non prevediamo un uso molto importante di questa funzionalità in modalità IE. È consigliabile distribuire la modalità IE per un elenco di siti interni attendibili e usare Application Guard solo per i siti non attendibili. Assicurarsi che tutti i siti in modalità IE o gli indirizzi IP vengano aggiunti anche ai criteri di Isolamento della rete per essere considerati come risorsa attendibile da Application Guard.

### <a name="do-i-need-to-install-the-application-guard-chrome-extension"></a>È necessario installare l'estensione Application Guard per Chrome?

No, la funzionalità Application Guard è supportata in modo nativo in Microsoft Edge. In effetti, l'estensione Application Guard per Chrome non è una configurazione supportata in Microsoft Edge.

### <a name="can-employees-download-documents-from-the-application-guard-edge-session-onto-host-devices"></a>I dipendenti possono scaricare documenti dalla sessione Edge di Application Guard nei dispositivi host?

In Windows 10 Enterprise edition, versione 1803, gli utenti sono in grado di scaricare documenti dal contenitore application guard isolato al PC host. Questa funzionalità è gestita dai criteri.

In Windows 10 Enterprise Edition, versione 1709 o Windows 10 Professional edition, versione 1803, non è possibile scaricare file dal contenitore Application Guard isolato nel computer host. Tuttavia, i dipendenti possono usare le opzioni Stampa su PDF o Stampa su XPS e salvare i file nel dispositivo host.

### <a name="can-employees-copy-and-paste-between-the-host-device-and-the-application-guard-edge-session"></a>I dipendenti possono copiare e incollare tra il dispositivo host e la sessione Edge di Application Guard?

A seconda delle impostazioni dell'organizzazione, i dipendenti possono copiare e incollare immagini (.bmp) e testo da e verso il contenitore isolato.

### <a name="why-dont-employees-see-their-favorites-in-the-application-guard-edge-session"></a>Perché i dipendenti non vedono i preferiti nella sessione di Application Guard Edge?

A seconda delle impostazioni dell'organizzazione, la sincronizzazione dei Preferiti potrebbe essere disattivata. Per gestire il criterio, vedere: Microsoft Edge e Microsoft Defender Application Guard | Documenti Microsoft.

### <a name="why-arent-employees-able-to-see-their-extensions-in-the-application-guard-edge-session"></a>Perché i dipendenti non sono in grado di visualizzare le estensioni nella sessione di Application Guard Edge?

Assicurati di abilitare il criterio delle estensioni nella configurazione di Application Guard.

### <a name="my-extension-doesnt-seem-to-work-in-edge-application-guard"></a>L'estensione non sembra funzionare in Edge Application Guard?

Se il criterio delle estensioni è abilitato per MDAG nella configurazione, verificare se l'estensione richiede componenti di gestione dei messaggi nativi, tali estensioni non sono supportate nel contenitore di Application Guard.

### <a name="im-trying-to-watch-playback-video-with-hdr-why-is-the-hdr-option-missing"></a>Sto cercando di guardare il video di riproduzione con HDR, perché manca l'opzione HDR?

Perché la riproduzione video HDR funzioni nel contenitore, l'accelerazione hardware vGPU deve essere abilitata in Application Guard.

### <a name="are-there-any-other-platform-related-faqs"></a>Ci sono altre domande frequenti relative alla piattaforma?

Sì. [Domande frequenti: Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Video: isolamento del browser per Microsoft Edge tramite Application Guard](https://www.youtube.com/watch?v=zQjaRqNXMqw&t=3s)
