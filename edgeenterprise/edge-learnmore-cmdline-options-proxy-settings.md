---
title: Impostazioni proxy di Microsoft Edge
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'Usare le opzioni della riga di comando per configurare le impostazioni proxy '
ms.openlocfilehash: 99a5f0776ea42f1e26050e0d30adb48a63907b8c
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980018"
---
# <a name="how-to-use-microsoft-edge-command-line-options-to-configure-proxy-settings"></a>Come usare le opzioni della riga di comando di Microsoft Edge per configurare le impostazioni proxy

In questo articolo viene descritto come è possibile usare le opzioni della riga di comando per sostituire le impostazioni di rete del sistema predefinite.

>[!NOTE]
>Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="system-network-settings"></a>Impostazioni di rete del sistema

Per impostazione predefinita, lo stack di rete di Microsoft Edge usa le impostazioni di rete del sistema. Sono incluse le *impostazioni proxy* e gli *archivi di certificai e chiavi private*.

Esistono scenari in cui gli utenti richiedono un'alternativa all'uso delle impostazioni proxy predefinite del sistema. Per supportare questi scenari, Microsoft Edge supporta le opzioni della riga di comando che puoi usare per configurare le impostazioni proxy personalizzate.

Queste opzioni della riga di comando corrispondono ai seguenti criteri nel gruppo **Server proxy**:

- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist)
- [ProxyMode](./microsoft-edge-policies.md#proxymode)
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl)
- [ProxyServer](./microsoft-edge-policies.md#proxyserver)
- [ProxySettings](./microsoft-edge-policies.md#proxysettings)

## <a name="command-line-options-for-proxy-settings"></a>Opzioni della riga di comando per le impostazioni proxy

Microsoft Edge supporta le opzioni della riga di comando correlate al proxy seguenti.

 **`--no-proxy-server`**
 
Indica a Microsoft Edge di non usare un proxy, anche se il sistema è configurato in altro modo per usarne uno. Sostituisce tutte le altre impostazioni proxy fornite.

**`--proxy-auto-detect`**

Indica a Microsoft Edge di provare a rilevare automaticamente la configurazione del proxy. Questo argomento viene ignorato se `--proxy-server` è configurato.

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

Indica a Microsoft Edge di usare una configurazione proxy personalizzata. Puoi specificare una configurazione proxy personalizzata in tre modi.

1. Specificare un mapping dello schema di elenchi a coppie di URL/porte separato da punto e virgola. Ad esempio, `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` indica a Microsoft Edge di usare il proxy HTTP "proxy1:8080" per gli URL http e il proxy HTTP "ftpproxy:80" per gli URL ftp.
2. Fornire un singolo URI con porta facoltativa da usare per tutti gli URL. Ad esempio, `--proxy-server="proxy2:8080"` userà il proxy in "proxy2:8080" per tutto il traffico.
3. Usare il valore "direct://" speciale. Ad esempio, `--proxy-server="direct://"` stabilirà che tutte le connessioni non useranno un proxy. 

>[!NOTE]
>Puoi configurare Microsoft Edge per provare a usare un proxy e un'opzione di fallback per il passaggio diretto se il proxy non è disponibile. Ad esempio: `--proxy-server="http://proxy2:8080,direct://`.

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

Indica a Microsoft Edge di ignorare qualsiasi proxy specificato per l'elenco di host separati da punto e virgola specificato. Questo flag deve essere usato con `--proxy-server`.

>[!NOTE]
>La corrispondenza del dominio finale non richiede separatori "." e quindi "\*microsoft.com" corrisponderà a "imicrosoft.com". Ad esempio, `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` userà il server proxy "proxy2" sulla porta 8080 per tutti gli host ad eccezione delle richieste per \*.microsoft.com, example.com e 127.0.0.1 sulla porta 8080. Nell'esempio precedente, le richieste di imicrosoft.com verranno ancora inoltrate tramite proxy. Tuttavia, le richieste iexample.com ignorano il proxy perché è stato specificato \*example.com anziché \*.example.com.

**`--proxy-pac-url=<pac-file-url>`**

Indica a Microsoft Edge di usare il file PAC nell'URL specificato. Ad esempio, `--proxy-pac-url="https://wpad/proxy.pac"` indica a Microsoft Edge di risolvere le informazioni proxy per le richieste URL usando il file **proxy.pac**.

## <a name="content-license"></a>Licenza dei contenuti

> [!NOTE]
> Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/). La pagina originale è disponibile [qui](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.

## <a name="see-also"></a>Vedere anche

- Per visualizzare le impostazioni di configurazione avanzate e le opzioni aggiuntive, vedi la [documentazione del proxy](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) nel progetto open source Chromium.
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)