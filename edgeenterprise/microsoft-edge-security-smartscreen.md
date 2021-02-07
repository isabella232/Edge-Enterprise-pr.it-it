---
title: Supporto di Microsoft Edge per Microsoft Defender SmartScreen
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Supporto di Microsoft Edge per Microsoft Defender SmartScreen
ms.openlocfilehash: 2de93b4ebe26b4a90592f7ee9143f6f775b682ce
ms.sourcegitcommit: c290b0b0fa6b7d7f94dcdfdda91302da733326ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314689"
---
# Supporto di Microsoft Edge per Microsoft Defender SmartScreen

Questo articolo illustra i vantaggi dell'uso di Microsoft Defender SmartScreen, ne spiega il funzionamento e descrive come configurare questa funzionalità di Microsoft Edge.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

Microsoft Defender SmartScreen è un servizio usato da Microsoft Edge per garantire la sicurezza mentre navighi sul Web. Microsoft Defender SmartScreen offre un sistema di avviso precoce che informa gli utenti della presenza di siti Web sospetti che potrebbero commettere attacchi di phishing o provare a distribuire malware attraverso un attacco mirato. Per altre informazioni, guardare [il video: navigazione sicura in Microsoft Edge](microsoft-edge-video-security-smartscreen.md).

> [!NOTE]
> Prima di Windows 10, versione 1703 questa funzionalità si chiamava filtro SmartScreen se usata all'interno del browser e Microsoft SmartScreen se usata al di fuori del browser.

## Vantaggi di Microsoft Defender SmartScreen

Microsoft Defender SmartScreen offre diversi vantaggi, che sono riepilogati nell'elenco seguente. Questi vantaggi sono descritti in dettaglio nella [documentazione di Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen). I vantaggi sono:

- Supporto anti-phishing e anti-malware
- Protezione URL e app basata sulla reputazione
- Integrazione del sistema operativo
- Euristica e dati di diagnostica migliorati
- Gestione tramite Criteri di gruppo e Microsoft Intune
- Blocco degli URL associati ad applicazioni potenzialmente indesiderate

## Come funziona Microsoft Defender SmartScreen

Una serie di input contribuisce agli avvisi di Microsoft Defender SmartScreen. I dati vengono ricevuti da diverse origini, tra cui il feedback degli utenti, i provider di dati e i modelli di intelligence. Questi dati vengono quindi usati per identificare contenuto potenzialmente dannoso. Microsoft Defender SmartScreen controlla anche le app o i programmi di installazione delle app scaricati per verificare se sono dannosi. In entrambi gli scenari, Microsoft Defender SmartScreen avvisa adeguatamente gli utenti del contenuto sospetto.

### Analisi del sito

Microsoft Defender SmartScreen stabilisce se un sito è potenzialmente dannoso grazie agli accorgimenti che seguono:

- Analisi delle pagine Web visitate per eventuali indicazioni di comportamenti sospetti.
- Verifica dei siti visitati rispetto a un record dinamico dei siti dediti al phishing segnalati.

Se Microsoft Defender SmartScreen determina che una pagina è dannosa, una pagina di avviso informa l'utente che tale sito è segnalato come pericoloso. Lo screenshot seguente mostra un esempio di pagina di avviso di Microsoft Defender SmartScreen quando un utente cerca di aprire un sito Web dannoso.

![Pagina di blocco di Microsoft Defender SmartScreen per un collegamento al sito esterno](media/microsoft-edge-security-smartscreen/microsoft-edge-smartscreen-warning.png)

Agli utenti viene offerta la possibilità di segnalare un sito come attendibile o pericoloso nel messaggio di avviso. Per altre informazioni, vedere [come segnalare un sito](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe).

### Analisi file

Microsoft Defender SmartScreen determina se un'app o un programma di installazione di app scaricato può essere potenzialmente dannoso in base a diversi criteri, ad esempio il traffico, la cronologia, i precedenti risultati dell'applicazione antivirus e la reputazione degli URL.

- I file con una reputazione attendibile nota verranno scaricati senza alcun avviso.  
- I file con una reputazione dannosa nota mostrano un avviso che informa l'utente che il file è pericoloso ed è stato segnalato come dannoso. Lo screenshot successivo è un esempio di avviso per un file dannoso.

  ![Notifica di blocco di Microsoft Defender SmartScreen per un file con una cattiva reputazione](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-known-malicious.png)

- I file sconosciuti mostrano un avviso che informa l'utente che il download non ha un impatto noto e consiglia di prestare attenzione. Lo screenshot successivo è un esempio di avviso per un file sconosciuto.

  ![Notifica di blocco di Microsoft Defender SmartScreen per file con reputazione sconosciuta](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious.png)

Non tutti i programmi sconosciuti sono dannosi e lo scopo dell'avviso di file sconosciuto è quello di fornire contesto e indicazioni agli utenti che ne hanno bisogno, soprattutto se l'avviso non è previsto.

  ![Mantenere il file con una reputazione dannosa](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious-keep.png)

Gli utenti possono comunque scaricare ed eseguire l'applicazione facendo clic su **... | Mantieni | Mostra altro | Mantieni comunque**.

> [!TIP]
> **Per informazione dei clienti aziendali.** Per impostazione predefinita, Microsoft Defender SmartScreen consente agli utenti di ignorare gli avvisi. Dal momento che questa interazione con l'utente è potenzialmente rischiosa, è consigliabile rivedere le [impostazioni di criteri di gruppo consigliate](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization).

Per scoprire come Microsoft Defender SmartScreen risponde ai diversi scenari, vedere il [sito di demo](https://demo.smartscreen.msft.net/).

## Microsoft Defender SmartScreen e privacy degli utenti

Microsoft Defender SmartScreen protegge gli utenti mentre esplorano Internet usando un sistema di verifica della reputazione. Microsoft Edge passerà informazioni pertinenti sull'URL o sul file al servizio Microsoft Defender SmartScreen per avviare la verifica della reputazione. La verifica confronta il sito Web o il file con elenchi dinamici di siti e file noti come pericolosi. Tutte le richieste inviate al servizio Microsoft Defender SmartScreen sono crittografate con TLS. Il servizio restituisce i risultati della verifica della reputazione, che potrebbero comportare la visualizzazione di un avviso per il sito o il file in Microsoft Edge. Questi risultati vengono archiviati in locale nel dispositivo.

Il servizio Microsoft Defender SmartScreen archivia i dati sulle verifiche della reputazione. Quando vengono identificati nuovi siti, il servizio li aggiunge a un database dinamico di URL e file notoriamente dannosi. I dati sono archiviati in server Microsoft sicuri e vengono usati solo per i servizi di sicurezza Microsoft. I dati non verranno mai usati per identificare o puntare agli utenti in alcun modo. Con la cancellazione della cache, vengono cancellati tutti i dati relativi agli URL di Microsoft Defender SmartScreen archiviati localmente. La cancellazione della cronologia di download rimuove tutti i dati di SmartScreen archiviati localmente relativi ai download di file.

Per altre informazioni su Microsoft Defender SmartScreen e sulla privacy in Microsoft Edge, vedere il [Whitepaper sulla privacy di Microsoft Edge](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen).

## Configurazione di Microsoft Defender SmartScreen per amministratori

Gli amministratori possono configurare Microsoft Defender SmartScreen usando le impostazioni di Criteri di gruppo, Microsoft Intune o gestione dei dispositivi mobili (MDM). In base alla configurazione di Microsoft Defender SmartScreen, è possibile mostrare agli utenti una pagina di avviso e consentire loro di visitare il sito oppure bloccarlo completamente.

### Configurazione di Microsoft Defender SmartScreen con Criteri di gruppo

Per un elenco completo dei criteri di SmartScreen, vedere [Impostazioni di Microsoft Defender SmartScreen](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings).

### Configurazione di Microsoft Defender SmartScreen con MDM

Per altre informazioni, vedi:

- [Impostazioni di Windows Intune per Microsoft Defender SmartScreen](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)
- [Impostazioni dei criteri MDM](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)

## Configurazione di Microsoft Defender SmartScreen per utenti

Microsoft Defender SmartScreen è attivato per impostazione predefinita per Microsoft Edge. Per disattivare Microsoft Defender SmartScreen, passare a *edge://settings/privacy > Servizi > Microsoft Defender SmartScreen*. Questa impostazione è uguale per tutti i profili associati all'installazione di Microsoft Edge in un dispositivo. Questa opzione non viene sincronizzata tra più dispositivi. L'impostazione si applica alla modalità InPrivate Browsing e Guest. Se un dispositivo viene gestito con i criteri di gruppo impostati da un'organizzazione, questa configurazione si rifletterà in *edge://settings/privacy*.

> [!NOTE]
> Gli utenti possono configurare Microsoft Defender SmartScreen per un singolo dispositivo, a meno che Criteri di gruppo o MDM non sia configurato per impedirlo. Per altre informazioni, vedere [Configurare e usare Microsoft Defender SmartScreen sui singoli dispositivi](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device).

## Domande frequenti

### Come funziona il sistema di verifica della reputazione?

Mentre navighi sul Web, Microsoft Defender SmartScreen classifica i siti Web e i download come traffico principale, pericoloso o sconosciuto. Il traffico principale si riferisce ai siti più popolari di cui Microsoft Defender SmartScreen ha determinato l'attendibilità. Se si visita un sito contrassegnato come pericoloso, Microsoft Defender SmartScreen blocca immediatamente l'accesso al sito. Quando si visita un sito sconosciuto, Microsoft DefenderSmartScreen ne verifica la reputazione per determinare se è opportuno accedervi.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: esplorazione sicura in Microsoft Edge](microsoft-edge-video-security-smartscreen.md)
- [Panoramica di Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)
- [Protezione dalle minacce](https://docs.microsoft.com/windows/security/threat-protection/index)
- [Proteggersi da applicazioni potenzialmente indesiderate](https://docs.microsoft.com/DeployEdge/microsoft-edge-potentially-unwanted-apps)