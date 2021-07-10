---
title: Condivisione cookie da Microsoft Edge a Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'Come condividere cookie da Microsoft Edge a Internet Explorer '
ms.openlocfilehash: 8f1a38106e49f71aa9d27f32cfecbd0df44eaf9f
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641842"
---
# <a name="cookie-sharing-from-microsoft-edge-to-internet-explorer"></a>Condivisione cookie da Microsoft Edge a Internet Explorer

>[!Note]
> L'applicazione desktop Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto il 15 giugno 2022 (per un elenco degli elementi nell'ambito, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. [Per altre informazioni, vedere](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Questo articolo spiega come configurare la condivisione dei cookie di sessione da un processo Microsoft Edge a un processo Internet Explorer, durante l'uso della modalità Internet Explorer.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 87 o successiva.

## <a name="prerequisites"></a>Prerequisiti

- Aggiornamenti di Windows

  - Windows 10 versione 2004, Windows Server versione 2004-KB4571744 o versioni successive
  - Windows 10 versione 1909, Windows Server versione 1909-KB4566116 o versioni successive
  - Windows 10 versione 1903, Windows Server versione 1903-KB4566116 o versioni successive
  - Windows 10 versione 1809, Windows Server versione 1809 e Windows Server 2019 - KB4571748 o successive
  - Windows 10 versione 1803 - KB4577032 o successive

- Microsoft Edge versione 87 o successive
- [Modalità IE](./edge-ie-mode.md)  configurata con l'Elenco siti modalità Enterprise

## <a name="overview"></a>Panoramica

Una configurazione comune nelle grandi organizzazioni consiste nell'avere un'applicazione che funzioni in un collegamento del browser moderno su un'altra applicazione, che potrebbe essere configurata per l'apertura in modalità Internet Explorer con Single Sign On (SSO) abilitato come parte del flusso di lavoro.

Per impostazione predefinita, i processi Microsoft Edge e Internet Explorer non condividono i cookie di sessione, che in alcuni casi possono risultare inconvenienti. Ad esempio, quando un utente deve autenticarsi nuovamente in modalità Internet Explorer o quando all’uscita da una sessione di Microsoft Edge non esce dalla sessione in modalità Internet Explorer. In questi scenari, è possibile configurare cookie specifici impostati da SSO per essere inviati da Microsoft Edge a Internet Explorer, in modo che l'esperienza di autenticazione diventi più fluida eliminando la necessità di eseguire nuovamente l'autenticazione.

> [!NOTE]
> I cookie di sessione possono essere condivisi solo da Microsoft Edge a Internet Explorer. Non è possibile condividere i cookie di sessione al contrario (da Internet Explorer a Microsoft Edge).

## <a name="how-cookie-sharing-works"></a>Funzionamento della condivisione dei cookie

Il linguaggio XML dell'elenco dei siti in modalità Enterprise è stato esteso in modo da consentire la condivisione di altri elementi da una sessione Microsoft Edge a Internet Explorer.  

La prima volta che si crea una scheda in modalità Internet Explorer in una sessione Microsoft Edge, tutti i cookie corrispondenti vengono condivisi nella sessione di Internet Explorer. In seguito, ogni volta che un cookie che corrisponde a una regola viene aggiunto, eliminato o modificato, viene inviato come aggiornamento della sessione di Internet Explorer. Il set di cookie condivisi viene anche valutato nuovamente quando l'elenco dei siti viene aggiornato.

### <a name="updated-schema-elements"></a>Elementi dello schema aggiornati

La tabella seguente descrive l'elemento \<shared-cookie\> aggiunto per supportare la funzionalità di condivisione dei cookie.

| Elemento| Descrizione |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br>O<br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |**(Obbligatorio)** un elemento \<shared-cookie\> richiede al minimo un*dominio* (per i cookie di dominio) oppure un attributo *host* (per i cookie solo host) e un*nome* attributo.<br>Devono corrispondere esattamente al nome e al dominio del cookie rispettivamente. **Nota:** i sottodomini non corrispondono.<br><br>L'attributo di *dominio* viene utilizzato per i cookie di dominio (un punto iniziale è consentito ma facoltativo).<br>L'attributo *host* viene usato per i cookie solo host (un punto iniziale è un errore). Se non si specifica nessuno dei due o entrambi, verrà restituito un errore.<br>* Un cookie è un cookie di dominio se un dominio è stato specificato nella stringa del cookie (tramite l'intestazione della risposta HTTP Set-Cookie o l'API document.cookie JS). Un cookie di dominio si applica al dominio specificato e a tutti i sottodomini. Se non è stato specificato un dominio nella stringa del cookie, il cookie è solo host e si applica solo all'host specifico per cui è stato impostato. Alcune classi di URL come nomi host composti da una sola parola, ad esempio http://intranetsite) e indirizzi IP come http://10.0.0.1), possono solo impostare i cookie solo host.    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | **(Facoltativo)** è possibile specificare un *percorso* di attributo. Se non viene specificato alcun percorso di attributo, oppure se è vuoto, i cookie che corrispondono a dominio/host e nome corrispondono al criterio, indipendentemente dal percorso (regola jolly).<br><br>Se è specificato un percorso, deve essere una corrispondenza esatta.<br>Se un cookie corrisponde a una regola con un percorso, avrà la precedenza su una regola priva di percorso. |

#### <a name="sharing-example"></a>Esempio di condivisione

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## <a name="see-also"></a>Vedere anche

- [Informazioni sulla modalità IE](./edge-ie-mode.md)
- [Informazioni sui siti configurabili](./edge-learnmore-configurable-sites-ie-mode.md)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)