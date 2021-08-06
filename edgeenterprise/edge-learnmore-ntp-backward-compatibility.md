---
title: Compatibilità con le versioni precedenti per la nuova pagina della scheda Enterprise
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Compatibilità con le versioni precedenti per la nuova pagina della scheda Enterprise
ms.openlocfilehash: 9643a7009fdc60859efaadc2adff6e47ce0918567195e9745a4a93c151aefc80
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724219"
---
# <a name="backwards-compatibility-for-the-enterprise-new-tab-page"></a>Compatibilità con le versioni precedenti per la nuova pagina della scheda Enterprise

Questo articolo descrive la variazione della nuova pagina della scheda e il modo in cui gli utenti possono garantire la compatibilità con Microsoft Edge versione 87 e versioni precedenti.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 87 o successiva.

## <a name="information-feeds-from-single-endpoint"></a>Feed informazioni da un unico endpoint

La nuova versione della pagina della scheda Enterprise coniuga i contenuti conformi a Microsoft 365 e i feed informazione pertinenti e conformi al settore, che vengono serviti tramite l'endpoint MSN.com.

> [!NOTE]
> I contenuti di Office 365 sono stati in origine serviti usando il dominio[](https://www.office.com)Office.com[.](https://www.office.com)

Se l'accesso al dominio MSN.com è limitato alla propria organizzazione, è consigliabile offrire agli utenti l'accesso a questo [URL](https://ntp.msn.com).

Qualora fosse necessario più tempo per abilitare l'accesso al dominio MSN, si consiglia di usare [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype), che consente di scegliere l'esperienza feed di Microsoft News oppure Office 365 per la nuova pagina della scheda.

### <a name="keep-using-officecom"></a>Continuare a usare Office.com

 È possibile configurare il criterio **NewTabPageSetFeedType** per continuare a usare il dominio deprecato Office.com.

> [!IMPORTANT]
> Il criterio **NewTabPageSetFeedType** e il dominio Office.com che serve i contenuti Office 365 smetterà di funzionare una volta rilasciata la versione 90 di Microsoft Edge.

Le seguenti impostazioni del criterio faranno in modo che la nuova pagina della scheda Enterprise esegua il rendering dei contenuti dei documenti di Office dal dominio Office.com.

- Impostare il criterio come **Obbligatorio**.
- Impostare il valore del mapping del criterio su **Office (1) = esperienza feed di Office 365**.

Qualora non fosse possibile passare a Office.com, inviare il proprio feedback. Un'altra opzione consiste nel configurare [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) in modo che punti a un URL di endpoint consentito dall'organizzazione.

> [!NOTE]
> Il criterio **NewTabPageLocation** ha precedenza se il criterio **NewTabPageSetFeedType** è configurato.

## <a name="enterprise-users-will-now-get-microsoft-news-content-via-my-feed"></a>Ora gli utenti Enterprise otterranno i contenuti di Microsoft News Feed personale.

La nuova pagina della scheda Enterprise offrirà informazioni rilevanti di settore in **Feed personale** e il contenuto di Office 365 in una singola visualizzazione per gli utenti che hanno eseguito l'accesso con l'account di Azure Active Directory (Azure AD). Per gli utenti che hanno eseguito l'accesso all'account Azure Active Directory (Azure AD) e che hanno selezionato l'opzione Microsoft News nel riquadro a comparsa Impostazioni, la visualizzazione della nuova pagina della scheda verrà sostituita dal contenuto **Feed personale**. Quando verrà aperta una nuova scheda nel browser, l'aspetto sarà simile all'esempio indicato nello screenshot seguente.

![Nuova pagina della scheda che mostra il contenuto del Feed personale.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> Gli utenti che non hanno eseguito l'accesso con Azure AD continueranno a visualizzare il feed MSN News quando viene aperta una nuova scheda.

## <a name="page-layout"></a>Layout di pagina

Grazie alle modifiche apportate alla nuova pagina della scheda, il layout di pagina non dovrà più controllare due tipi di contenuto specifici (Office 365 e Microsoft News), in modo che l'interruttore attiva/disattiva contenuto non sia disponibile. Lo screenshot seguente mostra il riquadro a comparsa per il layout di pagina.

![Visualizzazione layout di pagina per la nuova pagina della scheda.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

Se si desidera continuare ad accedere ai contenuti di Microsoft News non collegati all'organizzazione, è necessario usare un profilo browser diverso. Passare a *edge://settings/profiles* e disconnettersi dal profilo Azure AD. Questa azione fornisce una visualizzazione standard della nuova scheda Enterprise. 

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Modalità Enterprise per Internet Explorer 11](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)