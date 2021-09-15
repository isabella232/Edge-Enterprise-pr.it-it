---
title: Mantenere lo spostamento nella pagina in modalità Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Mantenere lo spostamento nella pagina in modalità Internet Explorer
ms.openlocfilehash: 20b18d121c3babfaacffd4a08316b25be714d95e
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979865"
---
# <a name="keep-in-page-navigation-in-internet-explorer-mode"></a>Mantenere lo spostamento nella pagina in modalità Internet Explorer

È possibile usare questo criterio come soluzione temporanea per forzare lo spostamento nella pagina dei siti in modalità Internet Explorer (modalità IE) a rimanere in modalità Internet Explorer.

Lo spostamento nella pagina viene avviato da un collegamento, uno script o una maschera nella pagina corrente. Può essere anche avviato da un reindirizzamento lato server di un precedente tentativo di spostamento nella pagina. Al contrario un utente può avviare uno spostamento che non sia nella pagina, e indipendentemente dalla pagina corrente, in diversi modi usando i controlli del browser. Ad esempio, usando la barra degli indirizzi, il pulsante indietro o un collegamento preferito.

>[!NOTE]
>Questo articolo si applica a Microsoft Edge, versione 81 o successiva.

## <a name="prerequisites"></a>Prerequisiti

Per questo criterio sono necessari gli aggiornamenti di Windows seguenti:

- Windows 10, versioni 1909 e 1903; Windows Server, versioni 1909 e 1903  ([KB4532695](https://support.microsoft.com/help/4532695))
- Windows 10, versione 1809; Windows Server, versione 1809, e Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))
- Windows 10, versione 1803 ([KB4534308](https://support.microsoft.com/help/4534308))
- Windows 10, versione 1709 ([KB4534318](https://support.microsoft.com/help/4534318))


## <a name="about-this-policy"></a>Informazioni sul criterio

Questo criterio consente di identificare e configurare tutti i server di autenticazione usati dai propri siti in modalità Internet Explorer. Tuttavia, il criterio può comportare un'esperienza di navigazione incoerente poiché alcuni siti effettuano il rendering in modalità Internet Explorer e altre volte in modalità Microsoft Edge. Questa esperienza varia a seconda che lo spostamento al sito abbia avuto inizio da una pagina in modalità Internet Explorer. I siti non configurati in modo esplicito per l'apertura in un motore di rendering specifico sono soggetti a questa incoerenza.

Se si abilita questo criterio, è consigliabile disabilitarlo dopo aver identificato tutti i server di autenticazione e averli aggiunti all'elenco del sito come server neutri. In questo modo, i siti moderni non effettueranno mai inavvertitamente il rendering in modalità Internet Explorer.

## <a name="keep-in-page-navigation-in-ie-mode"></a>Mantenere lo spostamento nella pagina in modalità IE

Per mantenere lo spostamento automatico o tutto lo spostamento nella pagina in modalità Internet Explorer, seguire i passaggi seguenti:

1. Aprire l'Editor Criteri di gruppo locali.
2. Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.
3. In **impostazione** fare doppio clic su **Specificare il comportamento degli spostamenti "nella pagina" verso i siti non configurati all'avvio dalle pagine in modalità Internet Explorer**.

   ![Impostazione dei criteri nella pagina](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. Seleziona **Attivato**. 

   ![Abilitazione dei criteri nella pagina](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. Scegliere una delle seguenti opzioni dall'elenco a discesa:

   - **Impostazione predefinita**: solo i siti configurati per l'apertura in modalità Internet Explorer verranno aperti in questa modalità. I siti non configurati per l'apertura in modalità Internet Explorer verranno reindirizzati a Microsoft Edge.
   - **Mantenere solo lo spostamento automatico in modalità Internet Explorer**: usare questa opzione se si vuole mantenere l'esperienza predefinita tranne gli spostamenti automatici (ad esempio 302 reindirizzamenti) ai siti non configurati in modalità Internet Explorer.
   - **Mantenere tutti gli** spostamenti nella pagina in modalità Internet Explorer (scelta consigliata **_minima):_** tutti gli spostamenti dalle pagine caricate in modalità Internet Explorer ai siti non configurati vengono mantenuti in modalità Internet Explorer.

6. Fare clic su **OK** o su **Applica** per salvare queste impostazioni dei criteri.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
