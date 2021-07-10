---
title: Formato di filtro per i criteri URL di Microsoft Edge
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Informazioni sul formato di filtro usato per i criteri URLBlocklist e URLAllowlist di Microsoft Edge.
ms.openlocfilehash: e178dad518ff4bee07bf89d9faca3231ee6cf246
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642022"
---
# <a name="filter-format-for-url-list-based-policies"></a>Formato di filtro per criteri basati su elenchi di URL

Questo articolo descrive il formato di filtro usato per i criteri basati su elenco per gli URL di Microsoft Edge (ad esempio [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist) e [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="the-filter-format"></a>Formato di filtro

Il formato di filtro è:

```
    [scheme://][.]host[:port][/path][@query]
```

I campi nel formato di filtro sono:

| Campo | Descrizione |
| --- | --- |
| **schema** (*facoltativo*) | Può essere http://, https://, ftp://, edge:// e così via. |
| **host** (*obbligatorio*) | Deve essere un nome host valido ed è possibile utilizzare un carattere jolly ("\*"). Per disabilitare la corrispondenza dei sottodomini, includere un punto facoltativo (".") prima di **host**. È possibile specificare un singolo indirizzo IP letterale del nome host, ma i caratteri jolly non sono supportati per un indirizzo IP letterale del nome host. |
| **porta** (*facoltativo*) | I valori validi sono compresi tra 1 e 65535. |
| **percorso** (*facoltativo*) | Puoi usare qualsiasi stringa nel percorso. |
| **query** (*facoltativo*) | La **query** è costituita da token chiave-valore o solo chiave separati da un simbolo ("&"). Separa i token chiave-valore con un simbolo di uguale ("="). Per indicare una corrispondenza di prefisso, puoi usare un asterisco ("\*") alla fine della **query**. |

## <a name="comparing-the-filter-format-to-the-url-format"></a>Confronto tra il formato di filtro e il formato dell'URL

Il formato del filtro è simile al formato dell'URL, ad eccezione delle differenze seguenti:

- Se includi "user:pass", verrà ignorato. Ad esempio: http://user:pass@ftp.contoso.com/pub/example.iso.
- Se includi un identificatore di frammento ("#"), quest'ultimo e tutti gli elementi che seguono gli identificatori vengono ignorati.
- Puoi usare un carattere jolly ("*") come **host** e puoi aggiungere un punto (".") come prefisso.
- Puoi usare una barra ("/") o un punto (".") come suffisso per l'**host**. In questo caso, il suffisso viene ignorato.

## <a name="filter-selection-criteria"></a>Criteri di selezione del filtro

Il filtro selezionato per un URL è la corrispondenza più specifica trovata dopo l'elaborazione delle regole di selezione del filtro seguenti:

1. I filtri con la corrispondenza **host** più lunga sono selezionati per primi.
2. Dai filtri selezionati, qualsiasi filtro con uno schema o una porta non corrispondente viene ignorato.
3. Nei filtri rimanenti viene selezionato il filtro con il **percorso** corrispondente più lungo.
4. Nei filtri rimanenti viene selezionato il filtro con il set di token di query più lungo. In questo passaggio il filtro elenco Consentiti ha la precedenza sul filtro elenco Blocca se entrambi i filtri hanno la stessa lunghezza di **percorso** e lo stesso numero di token di **query**.
5. Se non è presente alcun filtro valido, il sottodominio più a sinistra viene rimosso dall'**host** e il processo di selezione viene riavviato dal passaggio 1. L'**host** con asterisco speciale ("*") è l'ultimo cercato e corrisponde a tutti gli host.
6. Se un filtro è disponibile, tale filtro blocca o consente la richiesta dell'URL.

   >[!NOTE]
   >Il comportamento predefinito consiste nel consentire la richiesta URL se non viene trovato alcun filtro.

## <a name="example-filter-selection-criteria"></a>Criteri di selezione del filtro di esempio

In questo esempio, quando si cerca una corrispondenza "https://sub.contoso.com/docs" la selezione del filtro sarà:

1. Ricerca di un filtro per "sub.contoso.com". Se viene trovato un filtro, la ricerca passa al passaggio 2. Se non viene trovato alcun filtro, viene eseguito un altro tentativo con "contoso.com", "com” e infine con "".
2. Nei filtri selezionati, quelli per cui non è presente "http" nello **schema** vengono rimossi.
3. Nei filtri rimanenti quelli con un numero di porta esatto diverso da "80" vengono rimossi.
4. Nei filtri rimanenti, quelli per cui non è presente "/docs" come prefisso del **percorso** vengono rimossi.
5. Nei filtri rimanenti viene selezionato e applicato il filtro con il prefisso del percorso più lungo. Se non viene trovato alcun filtro, il processo di selezione riparte dal passaggio 1. Il processo viene ripetuto con il sottodominio successivo.

### <a name="additional-filter-information"></a>Altre informazioni sui filtri

Se un filtro ha un punto (".") come prefisso dell'**host**, vengono filtrate solo le corrispondenze esatte dell'**host**. Ad esempio:

- "contoso.com" (senza punto) corrisponde a "contoso.com", "www.contoso.com" e "sub.www.contoso.com"
- ".www.contoso.com" (con un punto come prefisso) corrisponde solo a "www.contoso.com"

È possibile utilizzare una versione standard o personalizzata dello **schema**. Gli schemi standard supportati includono:

- _about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, and _wss_.

Qualsiasi altro **schema** viene considerato come **schema** personalizzato, ma sono consentiti solo i modelli _schema:*_ e _schema://*_. Ad esempio:

- "personalizzata:\*" o "personalizzata://\*" corrisponderà a "personalizzata:app"
- "personalizzata:app" o "personalizzata://app" non sono validi

**schema** e **host** non rispettano la distinzione tra maiuscolo e minuscole. Ad esempio:

- Il filtro "http://contoso.com" corrisponde a "HTTP://contoso.com", "http://contoso.COM" e "http://contoso.com"

**percorso** e **query** rispettano la distinzione tra maiuscole e minuscole. Ad esempio:

- Il filtro "http://contoso.com/path?query=A" non corrisponde a "http://contoso.com/Path?query=A" né a "http://contoso.com/path?Query=A". Corrisponde a "http://contoso.COM/path?query=A".

## <a name="content-license"></a>Licenza dei contenuti

> [!NOTE]
> Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/). La [pagina originale di Chromium è disponibile qui](https://www.chromium.org/administrators/url-blacklist-filter-format).
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
