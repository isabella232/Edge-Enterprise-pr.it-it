---
title: Aggiornamenti di Windows per Microsoft Edge
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Aggiornamenti di Windows per Microsoft Edge.
ms.openlocfilehash: 953becc459fe729f84d54da419481b3c6e26cc47
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313906"
---
# Aggiornamenti di Windows per supportare la prossima versione di Microsoft Edge

In questo articolo viene descritto in che modo Windows verrà aggiornato per supportare la prossima versione di Microsoft Edge.

> [!IMPORTANT]
> Consulta il [post del blog](https://aka.ms/EdgeLegacyEOS) del team di Microsoft Edge sulla fine del servizio della versione legacy di Microsoft Edge.

> [!NOTE]
> Questo articolo si applica al canale stable Microsoft Edge.

##  <a name="microsoft-edge-and-the-windows-release-cycle"></a>Microsoft Edge e il ciclo di rilascio di Windows

Nella prossima versione di Microsoft Edge sono disponibili funzionalità di aggiornamento più frequenti e più flessibili. Poiché le versioni del browser non sono associate alle versioni principali di Windows, le modifiche verranno apportate al sistema operativo per assicurarsi che la prossima versione di Microsoft Edge si adatti perfettamente a Windows. Di conseguenza, gli aggiornamenti delle funzionalità verranno rilasciati in un ciclo di 6 settimane (approssimativamente). Gli aggiornamenti per la sicurezza e la compatibilità verranno forniti in base alle esigenze.

##  <a name="updates-and-the-user-experience"></a>Aggiornamenti ed esperienza utente

Gli aggiornamenti non cambieranno l'esperienza utente finché non verrà installato il canale Stable della prossima versione di Microsoft Edge. L'installazione di Microsoft Edge Beta, Dev o Canary non attiverà alcuna modifica in Windows. Queste versioni del browser verranno installate insieme ai browser esistenti.

Quando vengono applicati tutti gli aggiornamenti E il canale Stable della prossima versione di Microsoft Edge viene installato a livello di sistema, su quest'ultimo avranno effetto le modifiche seguenti:

- Tutti i pin del menu Start, i riquadri e i collegamenti per la versione corrente di Microsoft Edge verranno migrati alla prossima versione di Microsoft Edge.
- Tutti i pin e i collegamenti della barra delle applicazioni per la versione corrente di Microsoft Edge verranno migrati alla prossima versione di Microsoft Edge.
- La prossima versione di Microsoft Edge verrà aggiunta alla barra delle applicazioni. Se la versione corrente di Microsoft Edge è già stata aggiunta, verrà sostituita.
- Per la prossima versione di Microsoft Edge verrà aggiunto un collegamento al desktop. Se per la versione corrente di Microsoft Edge è già presente un collegamento, verrà sostituito.
- La maggior parte dei protocolli che Microsoft Edge gestisce per impostazione predefinita verrà migrata alla prossima versione di Microsoft Edge.
- L'istanza corrente di Microsoft Edge verrà nascosta in tutte le esperienze utente nel sistema operativo, ad esempio impostazioni, tutte le app e tutte le finestre di dialogo di supporto per file o protocolli.
- Tutti i tentativi d avviare la versione corrente di Microsoft Edge verranno reindirizzati alla prossima versione di Microsoft Edge.

  > [!NOTE]
  > Le installazioni a livello di utente non attiveranno questi comportamenti.

Insieme alle modifiche precedenti, sono state apportate modifiche che verranno eseguite indipendentemente dal fatto che sia installato il canale Stable della prossima versione di Microsoft Edge.

- La registrazione di Microsoft Edge verrà annullata per i libri e i protocolli XML che la prossima versione di Microsoft Edge non supporta. Se un utente tenta di aprire questi protocolli, verrà visualizzata una finestra di dialogo che chiede di scegliere un'app predefinita. Per saperne di più sulle modifiche al supporto dei libri, leggi l'articolo sul [download un'app ePub per continuare a leggere e-book](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0).

##  <a name="timeline"></a>Sequenza temporale

Le modifiche necessarie per supportare l'esperienza descritta verranno distribuite con tre aggiornamenti per diverse versioni di Windows.

###  <a name="windows-versions-1903-and-1909"></a>Windows, versioni 1903 e 1909

- Prima serie di modifiche apportate all'aggiornamento facoltativo di luglio 2019 e distribuite con l'aggiornamento della sicurezza di agosto 2019.
- Seconda serie di modifiche apportate all'aggiornamento facoltativo di agosto 2019 e distribuite con l'aggiornamento della sicurezza di settembre 2019.

  > [!NOTE]
  > Questo è l'aggiornamento in seguito al quale verrà annullata la registrazione di Microsoft Edge per il protocollo XML.

- Terza serie di modifiche apportate all'aggiornamento facoltativo di settembre 2019 e distribuite con l'aggiornamento della sicurezza di ottobre 2019.

  > [!NOTE]
  > Questo è l'aggiornamento in seguito al quale Microsoft Edge non supporterà più gli eBook.

###  <a name="windows-versions-1709,-1803,-and-1809"></a>Windows versioni 1709, 1803 e 1809

- Prima serie di modifiche apportate all'aggiornamento facoltativo di agosto 2019 e distribuite con l'aggiornamento della sicurezza di settembre 2019.
- Seconda serie di modifiche apportate all'aggiornamento facoltativo di settembre 2019 e distribuite con l'aggiornamento della sicurezza di ottobre 2019.

  > [!NOTE]
  > Questo è l'aggiornamento in seguito al quale verrà annullata la registrazione di Microsoft Edge per il protocollo XML.

- Terza serie di modifiche apportate all'aggiornamento facoltativo di ottobre 2019 e distribuite con l'aggiornamento della sicurezza di novembre 2019.

  > [!NOTE]
  > Questo è l'aggiornamento in seguito al quale Microsoft Edge non supporterà più gli eBook.

Nella tabella seguente vengono forniti i dettagli per gli aggiornamenti specifici in ogni serie di modifiche.

| Windows 10 | Altre informazioni | Download necessario |
|--|--|--|
| Versione 1709 | [KB4525241](https://support.microsoft.com/help/4525241/windows-10-update-kb4525241) | [Aggiornamento cumulativo per Windows 10, versione 1709](https://www.catalog.update.microsoft.com/Search.aspx?q=4525241) |
| Versione 1803  | [KB4525237](https://support.microsoft.com/help/4525237/windows-10-update-kb4525237) | [Aggiornamento cumulativo per Windows 10, versione 1803](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4525237) |
| Versione 1809  | [KB4523205](https://support.microsoft.com/help/4523205/windows-10-update-kb4523205) | [Aggiornamento cumulativo per Windows 10, versione 1809](https://www.catalog.update.microsoft.com/Search.aspx?q=4523205) |
| Versioni 1903 e 1909 |[KB4517389](https://support.microsoft.com/help/4517389/windows-10-update-kb4517389)  | [Aggiornamento cumulativo per Windows 10, versioni 1903 e 1909](https://www.catalog.update.microsoft.com/Search.aspx?q=4517389) |

##  <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Documentazione di Microsoft Edge](https://docs.microsoft.com/DeployEdge/)
