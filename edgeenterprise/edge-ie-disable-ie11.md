---
title: Disabilitare Internet Explorer 11
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Informazioni su come disabilitare Internet Explorer 11 e usare la modalità Internet Explorer in Microsoft Edge.
ms.openlocfilehash: 08d1fe48bfc4614710f4a341a285048194a64794
ms.sourcegitcommit: 928714329d0b11575494f557498f69a8417a3289
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385336"
---
# <a name="disable-internet-explorer-11"></a>Disabilitare Internet Explorer 11

Questo articolo descrive come disabilitare Internet Explorer 11 come browser autonomo.

## <a name="prerequisites"></a>Prerequisiti

Sono necessari gli aggiornamenti di Windows seguenti e il software Microsoft Edge:

- Aggiornamenti di Windows

  - Windows 10, versione 2004, Windows Server versione 2004, Windows 10, versione 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) o versione successiva
  - Windows 10 versione 1909, Windows Server versione 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) o versione successiva
  - Windows 10 versione 1809, Windows Server versione 1809 e Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) o versione successiva
  - Windows 10, versione 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) o versione successiva
   - Versione iniziale di Windows 10 (luglio 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) o versione successiva
  - Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) o versione successiva
  - Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) o versione successiva
  
- Canale stabile di Microsoft Edge


## <a name="overview"></a>Panoramica

Per le organizzazioni che richiedono Internet Explorer 11 (IE11) per la compatibilità legacy, la modalità Internet Explorer (modalità IE) in Microsoft Edge offre un’esperienza senza interruzioni con un unico browser. Gli utenti possono accedere alle applicazioni legacy da Microsoft Edge senza dover tornare a IE11.

Dopo aver configurato la modalità IE, è possibile disabilitare IE11 come browser autonomo **senza influire sul funzionamento della modalità IE** nell'organizzazione tramite i Criteri di gruppo.

> [!NOTE]
> Se è necessaria l'app autonoma IE11 per siti specifici e si vuole reindirizzare tutto il traffico del browser a Microsoft Edge, è possibile configurare il criterio [Invia tutti i siti non inclusi nell'elenco di siti a Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) per reindirizzare i siti da IE a Microsoft Edge.

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a>Esperienza utente dopo il reindirizzamento del traffico a Microsoft Edge

Quando viene abilitato il criterio **Disabilitare Internet Explorer 11 come browser autonomo**, tutte le attività di IE11 vengono reindirizzate a Microsoft Edge e l’esperienza utente è quella descritta di seguito:

- L'icona di IE11 nel menu Start verrà rimossa, ma quella sulla barra delle applicazioni rimarrà.
- Quando gli utenti proveranno ad avviare collegamenti o associazioni di file che usano IE11, verranno reindirizzati ad aprire lo stesso file/URL in Microsoft Edge.
- Quando gli utenti proveranno ad aprire IE11 richiamando direttamente il file binario iexplore.exe, si aprirà Microsoft Edge.

Nell’ambito dell'impostazione dei criteri per questa esperienza, è possibile mostrare un messaggio di reindirizzamento per ogni utente che prova ad aprire IE11. Si può impostare questo messaggio in modo che si visualizzi "Sempre" o "Una volta per utente". Per impostazione predefinita, il messaggio di reindirizzamento mostrato nello screenshot successivo non viene mai visualizzato.

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="Avviso quando si prova ad aprire IE dopo che è stato attivato un reindirizzamento a Microsoft Edge.":::

Se l'elenco dei siti per la modalità Enterprise contiene applicazioni configurate per l'apertura nell'app IE11 e IE11 viene disabilitato con questo criterio, tali applicazioni verranno aperte in modalità IE su Microsoft Edge.
> [!NOTE]
> Si verifica un problema con il flusso dell’utente quando un sito è configurato per l'apertura in IE11 ed è impostato il criterio Disabilitare IE11. Il problema è attualmente in corso di analisi.

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a>Disabilitare Internet Explorer 11 come browser autonomo

Per disabilitare Internet Explorer 11 tramite i Criteri di gruppo, seguire la seguente procedura:

1. Scaricare e installare il  [Modello dei criteri di Microsoft Edge](https://www.microsoft.com/en-us/business/download) più recente.
2. Aprire l'Editor Criteri di gruppo.
3. Passare a ***Configurazione computer/Modelli amministrativi/Componenti di Windows/Internet Explorer***. 
4. Fare doppio clic su ** Disabilitare Internet Explorer 11 come browser autonomo.**
5. Selezionare **Abilitato.**
6. In **Opzioni**, selezionare uno dei valori seguenti:

   - **Mai**  se non si vuole avvertire gli utenti che IE11 è disabilitato.
   - **Sempre**  se si vuole inviare una notifica agli utenti ogni volta che vengono reindirizzati da Internet 11.
   - **Una volta per utente**   se si vuole inviare una notifica agli utenti solo la prima volta che vengono reindirizzati.

7. Fare clic su **OK** o **Applica**  per salvare questa impostazione dei criteri.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [Informazioni aggiuntive sulla modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
