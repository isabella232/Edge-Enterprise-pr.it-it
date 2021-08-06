---
title: Strategia di configurazione sito Enterprise
ms.author: shisub
author: shisub
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Una guida dettagliata alla configurazione dell'elenco dei siti modalità Enterprise per la modalità Internet Explorer.
ms.openlocfilehash: ec0d1364f3db00bc78e29bab8abbfcf1748f68494791fd5288a435a8b1230018
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724419"
---
# <a name="enterprise-site-configuration-strategy"></a>Strategia di configurazione sito Enterprise

>[!Note]
> L'applicazione desktop di Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto il 15 giugno 2022 (per un elenco degli elementi interessati, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. [Altre informazioni qui](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Questo articolo descrive le modifiche apportate all'elenco dei siti in modalità Enterprise per supportare la modalità Internet Explorer per Microsoft Edge, versione 77 e successive.

Per altre informazioni sullo schema per il file XML dell'elenco di siti in modalità Enterprise, vedere [Indicazioni per lo schema v.2 della modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.
<!--
## Updated schema elements

The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:

| **Element** | **Description** |
| --- | --- |
| \<open-in app="**true**"\> | A child element that controls what browser is used for sites. This element is required for sites that need to **open in IE11**.|

**Example:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

The following table shows the possible values of the \<open-in\> element:

| **Value** | **Description** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Opens the site in IE mode or a full IE11 window. To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Opens the site in a full IE11 window |
| **\<open-in\>MSEdge\</open-in\>** | Opens the site in Microsoft Edge |
| **\<open-in\>None or not specified\</open-in\>** | Opens the site in the default browser or in the browser where the user navigated to the site. |
|**\<open-in\>Configurable\</open-in\>** | Allows the site to participate in IE mode engine determination. To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_. Adding it to the other 'open-in' elements won't change browser behavior.   -->

## <a name="configuration-strategy"></a>Strategia di configurazione

I passaggi seguenti fanno parte di una strategia di configurazione del sito per la modalità IE:
1. Preparare l'elenco dei siti
2. Configurare i siti neutri
3. (Facoltativo) Utilizzare la condivisione dei cookie, se necessario

<!--
Step 1.  – if you don’t have one use Site Discovery Step-by-Step
Step 2 – Neutral sites + sticky mode
        Use more examples and explain sticky mode better
Step 3 – If that doesn’t cover your needs, then use Cookie sharing -->

## <a name="prepare-your-site-list"></a>Preparare l'elenco dei siti

Se si dispone già di un elenco di siti in modalità Enterprise per IE11 o Microsoft Edge Legacy, è possibile riutilizzarlo per configurare la modalità IE.

Tuttavia, se non si dispone di un elenco di siti, è possibile utilizzare lo strumento [Enterprise Site Discovery tool](/deployedge/edge-ie-mode-site-discovery) per popolare l'elenco dei siti.

## <a name="configure-neutral-sites"></a>Configurare i siti neutri

Per il corretto funzionamento della modalità IE, i server SSO (Single Sign-On) di autenticazione e autenticazione dovranno essere configurati in modo esplicito come siti neutri. In caso contrario, le pagine in modalità IE tenteranno di reindirizzare a Microsoft Edge e l'autenticazione avrà esito negativo.

Quando viene avviata la navigazione, un sito neutrale usa il browser Microsoft Edge o la modalità IE. La configurazione dei siti neutri garantisce che le applicazioni che usano tali server di autenticazione, moderni e legacy, continuino a funzionare.

È possibile configurare i siti neutri impostando l'elenco a discesa *Apri in* su 'Nessuno' nello strumento Enterprise Mode Site List Manager o aggiornando direttamente il file XML dell'elenco siti:

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

Per identificare i server di autenticazione, analizzare il traffico di rete da un'applicazione che usa gli strumenti di sviluppo di IE11. Se serve più tempo per identificare i server di autenticazione, è possibile configurare un criterio in modo che tutti gli spostamenti nella pagina rimangano in modalità IE per consentire agli utenti di proseguire i loro flussi di lavoro senza interruzioni. Per ridurre al minimo l'uso della modalità IE quando non è necessario, disabilitare questa impostazione dopo aver identificato e aggiunto i server di autenticazione all'elenco dei siti. Per ulteriori informazioni, vedere [Mantenere lo spostamento nella pagina in modalità IE](/deployedge/edge-learnmore-inpage-nav).

>[!NOTE]
   >Lo schema per la modalità Enterprise v.1 non è supportato per l'integrazione della modalità Internet Explorer. Se attualmente usi lo schema v.1 con Internet Explorer 11, devi eseguire l'aggiornamento allo schema v.2. Per altre informazioni, vedere [Indicazioni per lo schema v.2 della modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).

## <a name="optional-use-cookie-sharing-if-necessary"></a>(Facoltativo) Utilizzare la condivisione dei cookie, se necessario

Per impostazione predefinita, i processi di Microsoft Edge e Internet Explorer non condividono i cookie di sessione e questa mancanza di condivisione può essere scomoda in alcuni casi durante l'uso della modalità IE. Ad esempio, quando un utente deve eseguire di nuovo l'autenticazione in modalità IE se in precedenza è abituato a farlo o quando si disconnette da una sessione di Microsoft Edge non si disconnette dalla sessione in modalità Internet Explorer per le transazioni critiche. In questi scenari, è possibile configurare cookie specifici impostati da SSO per l'invio da Microsoft Edge a Internet Explorer in modo che l'esperienza di autenticazione diventi più semplice eliminando la necessità di eseguire di nuovo l'autenticazione. Per altre informazioni, vedere [Condivisione cookie da Microsoft Edge a Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare).

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](./edge-ie-mode.md)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
