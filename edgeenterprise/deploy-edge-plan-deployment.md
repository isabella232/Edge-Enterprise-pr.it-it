---
title: Pianifica la distribuzione di Microsoft Edge
ms.author: collw
author: appcompatguy
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Pianifica la distribuzione di Microsoft Edge
ms.openlocfilehash: aae219bf44e78edabc02974a434d7d7efc1665eb
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447820"
---
# <a name="plan-your-deployment-of-microsoft-edge"></a>Pianifica la distribuzione di Microsoft Edge

In questo articolo vengono descritte le procedure consigliate per la distribuzione di Microsoft Edge in un ambiente aziendale.

>[!NOTE]
>Questo articolo si applica a Microsoft Edge versione 77 o successiva.

Le sezioni seguenti forniscono indicazioni specifiche per la pianificazione della distribuzione di Microsoft Edge.

- [Valutare l'ambiente e i requisiti del browser](#evaluate-your-existing-browser-environment-and-browser-needs)
- [Assicurare che i dispositivi Windows 10 siano pronti](#make-sure-your-windows-10-devices-are-ready)
- [Scegliere il metodo di distribuzione](#determine-your-deployment-methodology)
- [Esegui l'individuazione dei siti](#do-site-discovery)
- [Scegliere la strategia di canale](#determine-your-channel-strategy)
- [Definire e configurare i criteri](#define-and-configure-policies)
- [Verificare la compatibilità delle app](#do-app-compatibility-testing)
- [Distribuzione pilota di Microsoft Edge](#deploy-microsoft-edge-to-a-pilot-group)
- [Valutare la distribuzione pilota](#validate-your-deployment)
- [Distribuire Microsoft Edge nella grande impresa](#broad-deployment-of-microsoft-edge)

## <a name="evaluate-your-existing-browser-environment-and-browser-needs"></a>Valuta l'ambiente e le esigenze del browser esistenti

Prenditi tempo per comprendere lo stato corrente del browser e la visione del progetto per garantire che tutte le parti interessate siano allineate e lavorino per lo stesso risultato.

Inizia definendo lo stato corrente:

- Quali sono i browser attualmente distribuiti nel tuo ambiente?
- Quale browser è impostato come predefinito?
- Devi usare Internet Explorer per alcune delle tue app?
- Usi un elenco di siti per la modalità Enterprise per configurare Internet Explorer oggi?
- Quali piattaforme del sistema operativo sono supportate nel tuo ambiente? (Windows 10, macOS, Windows 7, Windows Server e così via).
- Quali strumenti di gestione vengono usati per la gestione del browser?
- Chi è responsabile della configurazione e della gestione del browser?
- Qual è il tuo processo per la convalida della compatibilità del browser?

Dopo aver compreso lo stato corrente, puoi determinare gli obiettivi desiderati per la distribuzione del browser, tenendo in considerazione quanto segue:

- Desideri [impostare Microsoft Edge come browser predefinito](./edge-default-browser.md)?
- Come [configurerai Microsoft Edge](./configure-microsoft-edge.md)?
- La configurazione di quali funzionalità è di fondamentale importanza nella distribuzione iniziale?
- Qual è il processo per la risoluzione dei problemi di compatibilità o configurazione identificati?

Devi anche comprendere i **prerequisiti** per le funzionalità che ti interessano, ad esempio:

- [Windows Defender Application Guard](/windows/security/threat-protection/windows-defender-application-guard/reqs-wd-app-guard)
- [Modalità Internet Explorer](./edge-ie-mode.md)
- [Autenticazione e sincronizzazione](./microsoft-edge-security-identity.md)

Tenendo a mente queste risposte, sei pronto a pianificare la distribuzione di Microsoft Edge.
<!--bookmark -->

## <a name="make-sure-your-windows-10-devices-are-ready"></a>Assicurati che i dispositivi Windows 10 siano pronti

Il canale Stable di Microsoft Edge richiede l'aggiornamento cumulativo più recente (LCU) da ottobre 2019 (o versione successiva). Se si tenta di eseguire la distribuzione in un dispositivo con Windows 10 con una versione precedente di LCU, l'installazione non andrà a buon fine. Per maggiori informazioni sugli LCU minimi che devono essere applicati prima della distribuzione di Edge, vedere [gli aggiornamenti di Windows per supportare la versione successiva di Microsoft Edge](./microsoft-edge-sysupdate-windows-updates.md).

## <a name="determine-your-deployment-methodology"></a>Determina la metodologia per la distribuzione

Dopo aver conosciuto lo stato finale desiderato, sei pronto per iniziare a pianificare come raggiungerlo. Le due modalità principali per la distribuzione di Microsoft Edge sono per ruolo e per sito.

### <a name="deploy-to-end-users-by-role"></a>Distribuzione agli utenti finali per ruolo

Se la compatibilità per le app è la tua preoccupazione principale e non hai una solida conoscenza delle app da testare, potresti voler prendere in considerazione la distribuzione agli utenti finali per ruolo. In questo modo, ogni ondata di una distribuzione in più fasi consente di fornire feedback e informazioni sulle app che potrebbero dover modificare la configurazione per risolvere i problemi di compatibilità.

### <a name="deploy-to-end-users-by-site"></a>Distribuzione agli utenti finali per sito

Se la larghezza di banda è la tua preoccupazione principale, è possibile prendere in considerazione la possibilità di eseguire i test di compatibilità delle applicazioni in anticipo. Dopo aver completato il test, esegui la distribuzione agli utenti finali per sito in modo da poter sfruttare la memorizzazione nella cache di altre ottimizzazioni di recapito del software.

## <a name="do-site-discovery"></a>Esegui l'individuazione dei siti

Se disponi di una dipendenza da applicazioni Web legacy e prevedi di utilizzare la modalità Internet Explorer (come la maggior parte dei clienti), dovrai probabilmente eseguire un'ulteriore individuazione dei siti.

### <a name="if-youve-already-deployed-and-configured-the-legacy-version-of-microsoft-edge"></a>Se hai già distribuito e configurato la versione legacy di Microsoft Edge

Se hai già configurato l'elenco dei siti aziendali in modo da funzionare per la versione legacy di Microsoft Edge, hai quasi fatto! Potrebbe essere necessario aggiungere solo i siti neutri.

I siti neutri sono in genere siti che forniscono Single Sign-On (SSO). Se esplori un sito neutro da Microsoft Edge, vorrai rimanere in Microsoft Edge per eseguire l'autenticazione. Se esplori un sito neutro in modalità Internet Explorer, vorrai rimanere in modalità Internet Explorer per eseguire l'autenticazione.

Identificare tutti i siti SSO (o altri siti neutri) utilizzati e aggiungerli all'elenco dei siti aziendali.

### <a name="if-youve-configured-internet-explorer-as-your-default-browser"></a>Se hai configurato Internet Explorer come browser predefinito

Se attualmente usi solo Internet Explorer, potresti non sapere quali siti sono stati aggiornati agli standard Web moderni e richiedono ancora Internet Explorer. Potresti voler cercare tali siti e aggiungerli all'elenco dei siti aziendali. Ciò ti consente di utilizzare la modalità Internet Explorer solo nei siti in cui è necessaria.

> [!TIP]
> Usa gli strumenti di [individuazione di siti aziendali](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery) per individuare i siti che potrebbero necessitare della modalità Internet Explorer. Puoi raccogliere dati nei computer che eseguono le versioni da Windows Internet Explorer 8 a Internet Explorer 11 in Windows10, Windows8.1 o Windows7.

### <a name="analyze-site-discovery-data"></a>Analisi dei dati di individuazione dei siti

Dopo aver raccolto i dati del sito, ti consigliamo di eseguire il processo in 4 passaggi riportato di seguito per analizzare i dati:

1. Ordina i dati in base al dominio, quindi in base all'URL.
2. Definisci i limiti di un'app da configurare per la modalità Internet Explorer. Desideri includere tutti i siti e i comandi Web che definiscono l'app. Tuttavia, non desideri includere siti e controlli aggiuntivi definendo l'app in modo troppo ampio. Alcuni siti possono essere semplici, ad esempio "http://contoso.com/app1", mentre altri possono richiedere la definizione di più siti e pagine.
3. Esegui un test dell'app per verificare che non funzioni in modo nativo. Molti siti offriranno contenuti moderni quando rilevano un browser moderno e offriranno solo contenuto legacy quando individuano Internet Explorer.
4. Aggiungi l'app all'elenco dei siti aziendali se non riesce a eseguire il test.

   > [!NOTE]
   > Come procedura consigliata, raggruppa tutti i siti che costituiscono un'app. Se tutti i siti devono essere utilizzati per eseguire un'unica attività e se tendono a essere aggiornati insieme, è un indice del fatto che debbano essere raggruppati. In questo modo, quando aggiorni un'app, è più facile rimuovere l'intero sito dalla modalità Internet Explorer e iniziare a usare un browser moderno per l'app specifica.

## <a name="determine-your-channel-strategy"></a>Determina la strategia del canale

Microsoft Edge viene rilasciato in [più canali](./microsoft-edge-channels.md).

> [!NOTE]
> Puoi installare più di un canale in un dispositivo

Il canale Stable è quello che vorrai distribuire nella maggior parte dei dispositivi. È tuttavia consigliabile considerare una strategia di distribuzione che includa più dispositivi e più canali.

### <a name="multiple-devices-and-channels"></a>Più dispositivi e canali

Si consiglia di disporre di un sottoinsieme rappresentativo di dispositivi configurati per l'utilizzo del canale Beta. In questo modo puoi visualizzare in anteprima le prossime modifiche apportate al browser. Puoi verificare se queste modifiche riguardano gli utenti finali o le app.

Potresti anche voler rendere disponibile il canale Dev (o anche il canale Canary) per alcuni ruoli, ad esempio gli sviluppatori Web. Valuta se vuoi scegliere alcuni dispositivi come destinazione con canali più fluidi e in rapida evoluzione o semplicemente rendere disponibili questi canali per consentire agli utenti di optare per l'installazione.

Poiché è possibile installare più canali in un dispositivo, puoi ridurre il rischio di test per gli utenti che hanno scelto di installare un canale non definitivo. Ad esempio, se un utente utilizza il canale Beta e si verifica un problema, puoi passare al canale Stable e continuare a lavorare. Questa operazione lo sblocca finché il problema non sarà risolto.

> [!NOTE]
> Se l'utente ha abilitato la sincronizzazione, la configurazione viene sincronizzata tra i canali, rendendo ancora più semplice la transizione tra i canali.

## <a name="define-and-configure-policies"></a>Definizione e configurazione dei criteri

Dopo aver creato l'elenco dei siti aziendali, ti consigliamo di identificare e configurare i criteri che intendi distribuire con Microsoft Edge. Questa operazione garantisce che questi criteri vengano applicati durante l'esecuzione dei test.

Per prima cosa, valuta l'esperienza della prima esecuzione che desideri far sperimentare agli utenti. Se vuoi importare automaticamente le impostazioni dal browser corrente, configura i criteri per [AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun)

Per i criteri di sicurezza, si consiglia di iniziare con la baseline di sicurezza di Microsoft Edge. La baseline di sicurezza può essere applicata utilizzando le [impostazioni baseline per la configurazione di sicurezza consigliata](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991) oppure utilizzando [Microsoft Intune](/intune/protect/security-baseline-settings-edge).

Per altri criteri, si consiglia di esaminare le configurazioni dei criteri per [Microsoft Edge](./microsoft-edge-policies.md) e gli [aggiornamenti di Microsoft Edge](./microsoft-edge-update-policies.md).

### <a name="define-your-update-strategy-and-policies"></a>Definizione dei criteri e della strategia di aggiornamento

Potrai inoltre voler determinare come desideri eseguire gli aggiornamenti dopo la distribuzione di Microsoft Edge:

- **Consenti a Microsoft Edge di aggiornarsi** (impostazione predefinita). Se scegli di consentire gli aggiornamenti automatici di Microsoft Edge, Microsoft Edge si aggiornerà automaticamente in base ai canali distribuiti.
- **Aggiorna Microsoft Edge al tuo ritmo**. Se preferisci controllare esplicitamente quando vengono distribuiti gli aggiornamenti, puoi disabilitare gli aggiornamenti automatici e distribuirli manualmente (vedi la [Guida di riferimento per i criteri degli aggiornamenti](./microsoft-edge-update-policies.md)). Dopo aver disabilitato gli aggiornamenti automatici, è possibile distribuire gli aggiornamenti per ciascun canale utilizzando uno degli strumenti seguenti:

- [Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
- [Configuration Manager](./deploy-edge-with-configuration-manager.md)
- lo strumento di distribuzione scelto da te.

Indipendentemente dalla strategia di aggiornamento, ti consigliamo di trarre vantaggio da una strategia di distribuzione con circuito. Con gli aggiornamenti automatici, ciò significa avere un campione rappresentativo di utenti che eseguono il canale Beta, per individuare i problemi con quello che diventerà il canale Stable. Con gli aggiornamenti manuali, questa operazione può includere anche una convalida aggiuntiva di un gruppo pilota dopo il rilascio di una nuova build del canale Stable. Questa operazione è seguita da un'ampia distribuzione.

>[!NOTE]
>Il supporto per Microsoft Edge si applica solo alla versione più recente di Microsoft Edge in ciascun canale

## <a name="do-app-compatibility-testing"></a>Esegui test di compatibilità delle app

La compatibilità delle applicazioni per Microsoft Edge è estremamente elevata, pertanto Microsoft fornisce le seguenti promesse di compatibilità:

1. Se funziona su Microsoft Edge *versione 45 e precedenti*, funzionerà su Microsoft Edge *versione 77 e successive*.
2. Se funziona su Internet Explorer, funzionerà su Microsoft Edge in modalità Internet Explorer.
3. Se funziona su Google Chrome, funzionerà su Microsoft Edge.

Se disponi di un'applicazione in cui non soddisfiamo questa promessa di compatibilità, manterremo la promessa per risolvere il problema tramite [App Assure di Microsoft](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure).

### <a name="internal-line-of-business-app-testing"></a>Collaudo delle app interne della divisione aziendale

Nonostante la nostra promessa per la compatibilità, sappiamo che molte organizzazioni devono convalidare alcune applicazioni per motivi di conformità o gestione dei rischi. Anche se ci aspettiamo che sia molto semplice, è importante essere organizzati e rigorosi nei test delle app.

Esistono 2 modi per eseguire i test di compatibilità delle app:

1. Test di laboratorio. Le applicazioni vengono convalidate in un ambiente strettamente controllato con configurazioni specifiche.
2. Test pilota. Le applicazioni vengono convalidate da un numero limitato di utenti nell'ambiente di lavoro giornaliero usando i propri dispositivi.

Scegli il metodo più appropriato per ogni app, per gestire i rischi senza investire eccessivamente nei test di compatibilità.

### <a name="third-party-app-support"></a>Supporto per app di terze parti

Oltre alle app interne delle proprie divisioni, molte organizzazioni usano app fornite da soggetti esterni. L'articolo [Pronto per Microsoft Edge](deploy-edge-ready-for-edge.md) contiene un elenco di applicazioni web che potrebbero essere in uso nella tua organizzazione. L'elenco contiene i collegamenti alle dichiarazioni dei produttori relative al supporto dei propri prodotti durante l'uso di Microsoft Edge. 

## <a name="deploy-microsoft-edge-to-a-pilot-group"></a>Distribuire Microsoft Edge a un gruppo pilota

Dopo aver definito i criteri e aver terminato i test di compatibilità delle app iniziali, sei pronto per la distribuzione al gruppo pilota. Esegui la distribuzione al gruppo pilota utilizzando uno degli strumenti seguenti:

- [Microsoft Intune per Windows](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)o [Microsoft Intune per macOS](/intune/apps/apps-edge-macos?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
- [Configuration Manager](./deploy-edge-with-configuration-manager.md).
- Un altro strumento di gestione, download e distribuzione del [file MSI per Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise).

## <a name="validate-your-deployment"></a>Convalida la tua distribuzione

Dopo aver distribuito il progetto pilota, desideri ricevere tutti i feedback degli utenti.

- Acquisisci feedback sulla compatibilità. Identifica i siti appartenenti all'elenco dei siti aziendali che non sono stati identificati durante l'individuazione del sito.
- Acquisisci feedback sulla configurazione dei criteri. Assicurati che gli utenti possano usare le funzionalità principali ed eseguire il loro lavoro seguendo le linee guida di sicurezza.
- Acquisisci feedback sulla facilità d'uso e sulle nuove funzionalità. Identifica le aree in cui è necessario sviluppare e recapitare la formazione in base alle domande dell'utente.

## <a name="broad-deployment-of-microsoft-edge"></a>Ampia distribuzione di Microsoft Edge

Dopo aver terminato il progetto pilota e aver aggiornato il piano di distribuzione con le lezioni apprese dal progetto pilota, sei pronto per eseguire una distribuzione completa di Microsoft Edge a tutti gli utenti.  Complimenti.

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: Distribuire Microsoft Edge](microsoft-edge-video-deploy.md)