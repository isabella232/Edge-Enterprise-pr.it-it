---
title: Reindirizzamento da Internet Explorer a Microsoft Edge per la compatibilità con i siti Web moderni
ms.author: laannade
author: dan-wesley
manager: ratetali
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Reindirizzamento da Internet Explorer a Microsoft Edge per la compatibilità con i siti Web moderni
ms.openlocfilehash: ec59380b82dc975ba3075d6e008bc0da05136f72
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979845"
---
# <a name="redirection-from-internet-explorer-to-microsoft-edge-for-compatibility-with-modern-web-sites"></a>Reindirizzamento da Internet Explorer a Microsoft Edge per la compatibilità con i siti Web moderni

> [!NOTE]
> Questo articolo si applica a Microsoft Edge Stable versione 87 o successiva.

## <a name="overview"></a>Panoramica

>[!Note]
> L'applicazione desktop Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto il 15 giugno 2022 (per un elenco degli elementi nell'ambito, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. [Per altre informazioni, vedere](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Molti siti Web moderni per come sono progettati non sono compatibili con Internet Explorer. Quando un utente di Internet Explorer visita un sito Web pubblico non compatibile, viene visualizzato un messaggio che lo informa che il sito Web non è compatibile con il browser in uso e che è necessario passare manualmente a un altro browser.

La necessità di passare manualmente a un altro browser è richiesta a partire da Microsoft Edge Stable versione 87.

Quando un utente accede a un sito Web non compatibile con Internet Explorer, verrà automaticamente reindirizzato a Microsoft Edge. Questo articolo descrive l'esperienza utente relativa al reindirizzamento e i criteri di gruppo utilizzati per configurare o disabilitare il reindirizzamento automatico.

> [!NOTE]
> Microsoft mantiene un elenco di tutti i siti Web non compatibili con Internet Explorer. Per altre informazioni, vedere [Richiedere aggiornamenti per l’elenco siti non compatibili](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)

## <a name="prerequisites"></a>Prerequisiti
- Microsoft Edge Versione stabile 87 o successiva
- Versioni di Windows
    - Windows 10 versione 1709 o successiva
    - Windows 8.1
    - Windows 7



## <a name="redirection-experience"></a>Esperienza di reindirizzamento

Durante il reindirizzamento a Microsoft Edge, viene visualizzata la finestra di dialogo una tantum illustrata nello screenshot seguente. Questa finestra di dialogo indica il motivo del reindirizzamento e richiede all’utente il consenso per copiare i dati e le preferenze di esplorazione da Internet Explorer a Microsoft Edge. Verranno importati i dati di esplorazione seguenti: Preferiti, password, motori di ricerca, schede aperte, cronologia, impostazioni, cookie e Home page.

![Notifica e prompt per l'importazione dei dati e delle preferenze.](media/edge-learnmore-neededge/neededge-dialog1.png)

Anche se l’utente non acconsente selezionando "Importa sempre i dati e le preferenze di esplorazione da Internet Explorer", è possibile fare clic su **Continua a esplorare** per continuare la sessione.

Infine, per ogni reindirizzamento viene visualizzato un banner sul sito Web non compatibile, illustrato nello screenshot seguente, sotto la barra degli indirizzi.

![Notifica sui siti Web moderni e prompt per configurare Microsoft Edge come browser predefinito o esplorare Microsoft Edge.](media/edge-learnmore-neededge/neededge-banner.png)

Banner sul sito Web non compatibile:

- consiglia all'utente di passare a Microsoft Edge
- consiglia di impostare Microsoft Edge come browser predefinito
- offre agli utenti la possibilità di esplorare Microsoft Edge

Quando un sito viene reindirizzato da Internet Explorer a Microsoft Edge, la scheda di Internet Explorer che aveva iniziato a caricare il sito Web viene chiusa se non ne aveva precedentemente caricato i contenuti. In caso contrario, la visualizzazione della scheda attiva passa a una pagina Web del  [supporto](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US)  Microsoft che informa l’utente del motivo per cui il sito Web è stato reindirizzato a Microsoft Edge.

> [!NOTE]
> Dopo il reindirizzamento, l’utente può tornare a utilizzare Internet Explorer per i siti Web non presenti nell'elenco di incompatibilità di Internet Explorer.  

## <a name="policies-to-configure-redirection-to-microsoft-edge"></a>Criteri per configurare il reindirizzamento a Microsoft Edge

> [!NOTE]
> Questi criteri saranno disponibili come aggiornamenti dei file ADMX entro il 26 ottobre 2020 e su Intune entro il 9 novembre 2020.

È necessario configurare tre criteri di gruppo per consentire il reindirizzamento automatico a Microsoft Edge. Tali criteri sono:

- RedirectSitesFromInternetExplorerPreventBHOInstall
- RedirectSitesFromInternetExplorerRedirectMode
- HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

### <a name="policy-redirectsitesfrominternetexplorerpreventbhoinstall"></a>Policy: RedirectSitesFromInternetExplorerPreventBHOInstall

Il reindirizzamento da Internet Explorer a Microsoft Edge richiede un oggetto browser helper (BHO) di Internet Explorer denominato "IEtoEdge BHO". Il criterio **RedirectSitesFromInternetExplorerPreventBHOInstall** verifica se il BHO è installato o meno.  

- Se si abilita questo criterio, il BHO necessario per il reindirizzamento non verrà installato e gli utenti continueranno a visualizzare i messaggi di incompatibilità per alcuni siti Web in Internet Explorer. Se il BHO è già installato, verrà disinstallato all’aggiornamento successivo del canale stabile Microsoft Edge.
- Se si disabilita o non si configura questo criterio, non viene installato il BHO. Questo è il comportamento predefinito.

Oltre alla necessità del BHO, esiste una dipendenza da **RedirectSitesFromInternetExplorerRedirectMode**, che deve essere impostata su "Reindirizza i siti in base all'elenco dei siti incompatibili" o su "Non configurato".

### <a name="policy-redirectsitesfrominternetexplorerredirectmode"></a>Policy: RedirectSitesFromInternetExplorerRedirectMode

 Questo criterio corrisponde all’impostazione**Browser predefinito** di Microsoft Edge "Consenti a Internet Explorer di aprire i siti Web in Microsoft Edge". Per accedere a questa impostazione, fare clic sull'URL seguente: *edge://settings/defaultbrowser*.  

- Se il criterio non viene configurato o impostato su "Sitelist", Internet Explorer reindirizza i siti Web non compatibili a Microsoft Edge. Questo è il comportamento predefinito.
- Per disabilitare questo criterio, selezionare **Abilitato** e quindi dall'elenco a discesa in Opzioni: Reindirizza i siti incompatibili da Internet Explorer a Microsoft Edge, selezionare **Disabilita**. In questo stato, i siti Web non compatibili non verranno reindirizzati a Microsoft Edge.

> [!NOTE]
> Se l’utente utilizza un dispositivo personale non gestito dall'organizzazione, viene visualizzata un'altra impostazione denominata "Consenti il caricamento dei siti nella modalità di Internet Explorer" nella sezione**compatibilità di Internet Explorer**.
>
>Questa opzione non verrà visualizzata per i dispositivi associati a dominio o registrati tramite Gestione di dispositivi mobili (MDM).
>
> In alternativa, se si desidera consentire agli utenti di caricare i siti Web nella modalità di Internet Explorer, è possibile farlo configurando il criterio [Consenti il test della modalità di Internet Explorer](./microsoft-edge-policies.md#intranetredirectbehavior).

### <a name="policy-hideinternetexplorerredirectuxforincompatiblesitesenabled"></a>Policy: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

Questo criterio configura l'esperienza utente per il reindirizzamento del sito Web non compatibile a Microsoft Edge.  

- Se si abilita questo criterio, gli utenti non visualizzano la finestra di dialogo una tantum di reindirizzamento e il banner di reindirizzamento. Non vengono importati dati o preferenze utente del browser.
- Se il criterio è disabilitato o non viene configurato, verrà visualizzata la finestra di dialogo di reindirizzamento al primo tentativo di reindirizzamento e il banner di reindirizzamento permanente per le sessioni avviate con un reindirizzamento.

  > [!NOTE]
  > I dati di esplorazione dell’utente verranno importati a ogni nuovo reindirizzamento. Tuttavia, questo si verifica solo se l'utente ha acconsentito all'importazione nella finestra di dialogo una tantum di reindirizzamento.

## <a name="disable-redirection-to-microsoft-edge"></a>Disabilitare il reindirizzamento a Microsoft Edge

Se si desidera disabilitare il reindirizzamento PRIMA di eseguire l'aggiornamento a Microsoft Edge Stable versione 87, effettuare la procedura seguente:

1. Impostare il criterio **RedirectSitesFromInternetExplorerPreventBHOInstall** su **Abilitato**.

Se si desidera disabilitare il reindirizzamento DOPO aver eseguito l'aggiornamento a Microsoft Edge Stable versione 87, effettuare la procedura seguente:

1. Impostare il criterio **RedirectSitesFromInternetExplorerRedirectMode** su **Abilitato** e quindi dall’elenco a discesa in Opzioni: Reindirizza i siti incompatibili da Internet Explorer a Microsoft Edge, selezionare **Disabilita**. Questa impostazione interrompe il reindirizzamento non appena il criterio avrà effetto.
2. Impostare il criterio **RedirectSitesFromInternetExplorerPreventBHOInstall** su **Abilitato**. Il BHO verrà disinstallato dopo il successivo aggiornamento di Microsoft Edge.

## <a name="see-also"></a>Vedere anche

- [Richiedere aggiornamenti per l’elenco siti non compatibili](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Criteri Microsoft Edge](./microsoft-edge-policies.md)