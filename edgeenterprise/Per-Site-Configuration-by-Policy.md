---
title: 'Configurazione per sito in base ai criteri '
ms.author: collw
author: AndreaLBarr
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'Configurazione per sito in base ai criteri '
ms.openlocfilehash: 4f1bf9a421f0098ba8105e78f77ac4af62530239
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979815"
---
# <a name="persite-configuration-by-policy"></a>Configurazione per sito in base ai criteri

## <a name="introduction-browsers-as-decision-makers"></a>Introduzione: Browser come entità decisionali

Man mano che ogni pagina viene caricata, il browser prende molte decisioni, tra cui: dovrebbe essere disponibile una particolare API? È necessario consentire il caricamento di una risorsa? L'esecuzione dello script deve essere consentita? L'elenco è lungo.

Nella maggior parte dei casi, le decisioni sono governate da due input: un'impostazione utente e l'URL della pagina per la quale viene presa la decisione.

Nella piattaforma Web legacy di Internet Explorer, ognuna di queste decisioni era denominata  [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29) e i Criteri di gruppo aziendali e le impostazioni utente all'interno del Pannello di controllo Internet controllavano come il browser avrebbe gestito ogni decisione.  

In Microsoft Edge, la maggior parte delle autorizzazioni per sito è controllata da impostazioni e criteri espressi utilizzando una semplice sintassi con supporto limitato di caratteri jolly. Le aree di sicurezza di Windows vengono ancora utilizzate solo per un numero limitato di decisioni di configurazione.

## <a name="background-windows-security-zones"></a>Background: Aree di sicurezza di Windows

Per semplificare la configurazione per l'utente o per l'amministratore, la piattaforma legacy ha classificato i siti in cinque diverse  **aree di sicurezza:** Computer locale, Intranet locale, Attendibile, Internet e Siti con restrizioni.

Quando si prende una decisione, il browser prima mappa il sito Web a una zona, quindi consulta l'impostazione di URLAction per tale zona per decidere cosa fare. Impostazioni predefinite come "Soddisfa automaticamente le verifiche di autenticazione dalla mia Intranet" stanno a significare che la maggior parte degli utenti non ha mai avuto bisogno di modificare alcuna impostazione rispetto ai valori predefiniti.

Gli utenti possono utilizzare il Pannello di controllo Internet per assegnare siti specifici alle zone e configurare i risultati delle autorizzazioni per ciascuna zona. Negli ambienti gestiti, gli amministratori possono utilizzare i Criteri di gruppo per assegnare siti specifici alle zone (tramite il criterio "Elenco di assegnazione da sito a zona") e specificare le impostazioni per URLActions in base alla zona. Oltre all'assegnazione manuale amministrativa o da parte dell'utente dei siti alle zone, l'euristica aggiuntiva potrebbe [ assegnare i siti alla zona Intranet locale](/archive/blogs/ieinternals/the-intranet-zone). In particolare, i nomi host senza punti (ad esempio `http://payroll`) sono stati assegnati all'area Intranet. Se è stato utilizzato uno script di configurazione proxy, tutti i siti configurati per ignorare il proxy verranno mappati all'area Intranet.

La Versione legacy di Microsoft Edge ha ereditato l'architettura delle zone dal suo predecessore Internet Explorer, con alcune modifiche semplificate:

- Le cinque zone integrate di Windows sono state ridotte a tre: Internet (Internet), Attendibile (Intranet+Attendibile) e Computer locale. L'area Siti con restrizioni è stata rimossa.

- I mapping da zona a URLAction sono stati codificati nel browser, ignorando i Criteri di gruppo e le impostazioni nel Pannello di controllo Internet.

## <a name="per-site-permissions-in-the-microsoft-edge"></a>Autorizzazioni per sito in Microsoft Edge

A differenza dei suoi predecessori, il nuovo Microsoft Edge fa un uso molto limitato delle aree di sicurezza di Windows. Al contrario, la maggior parte delle autorizzazioni e delle funzionalità che offrono agli amministratori la configurazione per sito tramite  [criteri](/deployedge/microsoft-edge-policies) si basano su elenchi di regole nel  [formato di filtro URL](/DeployEdge/edge-learnmmore-url-list-filter%20format).

Quando gli utenti finali aprono <code>edge://settings/content/siteDetails?site=https://example.com</code>, troveranno un lungo elenco di opzioni di configurazione ed elenchi per varie autorizzazioni. Gli utenti usano raramente direttamente la pagina delle impostazioni, invece di effettuano scelte durante l'esplorazione usando i vari widget e interruttori nell'elenco a discesa **Informazioni pagina** (visualizzato quando si fa clic sull'icona di blocco nella barra degli indirizzi) o tramite i vari prompt o pulsanti sul bordo destro della barra degli indirizzi.

Le aziende possono utilizzare i Criteri di gruppo per fornire elenchi di siti per i singoli criteri che controllano il comportamento del browser. Per trovare questi criteri, è sufficiente aprire la  [documentazione Microsoft Edge per i Criteri di gruppo](/deployedge/microsoft-edge-policies)  e cercare  **ForUrls**  per trovare i criteri che consentono e bloccano il comportamento in base all'URL del sito caricato. La maggior parte delle impostazioni pertinenti è elencata nella sezione  [Criteri di gruppo per Impostazioni contenuto](/deployedge/microsoft-edge-policies#content-settings).

Esistono anche diversi criteri (i cui nomi contengono  **Predefinito**) che controllano il comportamento predefinito per una determinata impostazione.

Molte delle impostazioni sono molto oscure (WebSerial, WebMIDI) e molto spesso non c'è motivo di modificare un'impostazione rispetto a quella predefinita (Immagini).

## <a name="common-questions"></a>Domande comuni

## <a name="q-can-the-url-filter-format-match-on-a-sites-ip-address"></a>D: Il formato del filtro URL può corrispondere all'indirizzo IP di un sito?

No, il formato non supporta la specifica di un intervallo IP per gli elenchi di indirizzi consentiti e bloccati. Supporta la specifica dei singoli IP  **letterali**, ma tali regole vengono rispettate solo se l'utente accede al sito utilizzando tale letterale (ad es. <http://127.0.0.1/>). Se viene utilizzato un nome host (<http://localhost>), la regola dell' IP letterale non verrà rispettata anche se l'IP risolto dell'host corrisponde all'IP elencato nel filtro.

## <a name="q-can-url-filters-matchjustdotless-host-names"></a>D: I filtri URL possono corrispondere solo a nomi host senza punti?

No. È necessario elencare singolarmente ogni nome host desiderato, ad esempio (`https://payroll`, `https://stock`, `https://who` e così via).

Se l'utente ha una prospettiva orientata verso il futuro, è possibile costruire la struttura della rete interna in modo che il formato del nome host sia:

- <div style="display: inline">`https://payroll.contoso-intranet.com`</div>

- <div style="display: inline">`https://timecard.contoso-intranet.com`</div>

- <div style="display: inline">`https://sharepoint.contoso-intranet.com`</div>

Congratulazioni, è stata implementata una procedura consigliata. È possibile configurare ogni criterio desiderato con una voce ***.contoso-intranet.com**  e l'intera rete Intranet verrà attivata.

## <a name="use-of-security-zones-inthe-microsoft-edge"></a>Utilizzo delle aree di sicurezza in Microsoft Edge

Sebbene Microsoft Edge si basi principalmente su criteri individuali utilizzando il formato del filtro URL, continua a utilizzare le aree di sicurezza di Windows per impostazione predefinita in un numero limitato di posizioni per semplificare la distribuzione all'interno delle aziende che storicamente si sono affidate alla configurazione delle aree. I comportamenti seguenti sono controllati dal criteri dell'area:

1. Quando si decide se rilasciare automaticamente le credenziali di autenticazione integrata di Windows (Kerberos/NTLM)

2. Quando si decide come gestire i download di file

3. Per la modalità Internet Explorer

## <a name="credential-release"></a>Rilascio delle credenziali

Per impostazione predefinita, Microsoft Edge valuterà URLACTION_CREDENTIALS_USE per decidere se l'autenticazione integrata di Windows viene utilizzata automaticamente o se l'utente deve invece visualizzare una richiesta di autenticazione manuale. La configurazione di un [criterio elenco siti AuthServerAllowlist](/deployedge/microsoft-edge-policies#authserverallowlist) impedirà la consultazione dei criteri delle aree.

## <a name="file-downloads"></a>Download di file

Prove sulle origini del download di file (il cosiddetto "[Mark of the Web](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/) viene registrato per i file scaricati dall'area Internet. Altre applicazioni (ad esempio Windows Shell, Microsoft Office, ecc.) possono prendere in considerazione questa prova dell'origine quando si decide come gestire un file.

Se il criterio dell'area di sicurezza di Windows è configurato su Disattiva l'impostazione Avvio di applicazioni e file non sicuri, il gestore download di Microsoft Edge bloccherà i download di file dai siti in quell'area con una nota: "Non è possibile scaricare - Bloccato".  

## <a name="ie-mode"></a>Modalità IE

La modalità IE può essere configurata per [ aprire tutti i siti Intranet in modalità IE.](/deployedge/edge-ie-mode#configure-all-intranet-sites) In questa configurazione, Edge valuta la zona di un URL quando decide se deve aprirsi o meno in modalità IE. Oltre a questa decisione iniziale, le schede in modalità IE eseguono Internet Explorer e, di conseguenza, valutano le impostazioni delle aree per ogni decisione sui criteri esattamente come Internet Explorer.

## <a name="summary"></a>Riepilogo

Nella maggior parte dei casi, le impostazioni di Microsoft Edge possono essere lasciate ai valori predefiniti. Gli amministratori che desiderano modificare le impostazioni predefinite per tutti i siti o siti specifici possono utilizzare i Criteri di gruppo appropriati per specificare gli elenchi di siti o i comportamenti predefiniti. In alcuni casi (rilascio delle credenziali, download di file e modalità IE), gli amministratori continueranno a controllare il comportamento configurando le impostazioni delle aree di sicurezza di Windows.
