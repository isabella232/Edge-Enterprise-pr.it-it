---
title: Pianificare la transizione in modalità tutto schermo
ms.author: aguta
author: aguta
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Pianificare la transizione in modalità tutto schermo
ms.openlocfilehash: 2a82852f10f2a842f28029738e72f72de4c53c41
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447850"
---
# <a name="plan-your-kiosk-mode-transition"></a>Pianificare la transizione in modalità tutto schermo

Il presente articolo fornisce indicazioni su come passare alla modalità tutto schermo da una versione legacy di Microsoft Edge a Microsoft Edge.  

> [!NOTE]
> L'articolo si applica ai canali Microsoft Edge Stable, Beta e Dev, versione 87 o successiva.

> [!IMPORTANT]
> Quando il supporto per la versione legacy di Microsoft Edge terminerà il 9 marzo 2021, verrà rimosso e sostituito con Microsoft Edge su Croromium come parte di Windows Update di aprile. Per informazioni dettagliate, vedere questo [post del blog](https://aka.ms/EdgeLegacyEOS). Per continuare a usare gli scenari di modalità tutto schermo basati su browser, è necessario installare Microsoft Edge su Chromium e configurare la modalità tutto schermo prima del rilascio nel dispositivo di Windows Update di aprile.

## <a name="kiosk-setup-steps"></a>Procedura di configurazione della modalità tutto schermo

Usare la procedura seguente come guida per configurare la modalità tutto schermo in Microsoft Edge.

**Passaggio 1: valutare le proprie esigenze rispetto alle funzionalità in modalità tutto schermo che saranno rilasciate (e imminenti).** La tabella seguente elenca le caratteristiche supportate dalla modalità tutto schermo su Chromium di Microsoft Edge e della versione legacy di Microsoft Edge. Usare questa tabella come guida per la transizione a Microsoft Edge, confrontando il modo in cui tali caratteristiche sono supportate in entrambe le versioni di Microsoft Edge.

|Funzionalità|Segnaletica digitale/interattiva|Esplorazione pubblica|Disponibile con la versione di Microsoft Edge (e versioni successive)|Disponibile con la versione legacy di Microsoft Edge|
|-|-|-|-|-|
|Spostamento InPrivate|S|S|89|S|
|Reimpostazione in caso di inattività|S|S|89|S|
|[Barra degli indirizzi di sola lettura](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (criterio) |N|S |89|N|
|[Eliminare i download all'uscita](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (criterio)  | S|S |89|N|
|F11 bloccato (entra/esci dalla modalità a schermo intero) | S | S | 89 |S|
|F12 bloccato (avvia Strumenti di sviluppo) | S | S | 89 |S|
| Supporto per più schede | N| S| 89|S|
|[Consente il supporto degli URL](./microsoft-edge-policies.md#urlallowlist) (criterio)|S|S|89|N|
|[Blocca il supporto degli URL](./microsoft-edge-policies.md#urlblocklist) (criterio)|S|S|89|N|
|[Mostra il pulsante Home](./microsoft-edge-policies.md#showhomebutton) (criterio)|N|S|89|S|
|[Gestione preferiti](./microsoft-edge-policies.md#managedfavorites) (criterio)|N|S|89|S|
|[Abilita la stampante](./microsoft-edge-policies.md#printingenabled) (criterio)|S|S|89|S|
|[Configura l'URL della pagina Nuova scheda](./microsoft-edge-policies.md#newtabpagelocation) (criterio)|N|S||S|
|Pulsante Termina sessione | N| S| 89|S|
|Tutti gli URL Microsoft Edge interni sono bloccati, ad eccezione di *edge://downloads* e *edge://print* |N|S|89|S|
| CTRL+N bloccato (apri una nuova finestra) | S | S | 89 |S|
| CTRL+T bloccato (apri una nuova scheda) |S | S | 89 |S|
|Impostazioni e altro (...) mostreranno solo le opzioni obbligatorie  |S |S |89 |S|
|Limitazione del lancio di altre applicazioni dal browser|S|S|90/91|S|
|Blocco delle impostazioni di stampa dell'interfaccia utente|S|S|90/91|S|
|[Imposta la pagina Nuova scheda come home page](./microsoft-edge-policies.md#homepageisnewtabpage) (criterio)|-|-|TBD|S|

> [!NOTE]
> Per informazioni sulla pianificazione dei rilasci di Microsoft Edge, consultare [il piano di rilascio di Microsoft Edge](microsoft-edge-release-schedule.md).

**Passaggio 2: testare la nuova modalità tutto schermo in Microsoft Edge.** È consigliabile testare la configurazione della modalità tutto schermo in Microsoft Edge. Un modo rapido e semplice per testare la modalità tutto schermo sta nel configurare una singola app di accesso assegnata usando le impostazioni di Windows, come descritto di seguito.

1. Installa l'ultima versione di Windows 10 Insider Preview, versione 20215 o successiva. Segui le istruzioni in [Introduzione alle build di Windows 10 Insider Preview](/windows-insider/get-started).
2. Installa l’ultima versione del [canale stabile Microsoft Edge](https://www.microsoft.com/edge), versione 87 o successiva.  Per testare le caratteristiche più recenti, puoi scaricare l’ultima versione del [canale Microsoft Edge Beta](https://www.microsoftedgeinsider.com/download), versione 89 o successiva.

   > [!IMPORTANT]
   > Poiché è richiesta un'installazione a livello di dispositivo, è supportato solo un canale non Canary.

3. Dal computer di un chiosco multimediale, apri le Impostazioni di Windows e digita "chiosco" nel campo di ricerca. Seleziona  **Configura un chiosco multimediale (accesso assegnato**), mostrato nella schermata successiva per aprire la finestra di dialogo per la creazione del chiosco.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

4. Nella pagina **Configura un chiosco multimediale** , fai clic su  **Inizia**.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="Pagina chiosco multimediale: Introduzione":::

5. Digita un nome per creare un nuovo account per chiosco multimediale o scegli un account esistente dall'elenco a discesa popolato e quindi fai clic su  **Avanti**.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="Modalità tutto schermo: crea un account":::

6. Nella pagina **Scegli un'app chiosco multimediale** , seleziona **Microsoft Edge** e quindi fai clic su  **Avanti**.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="Modalità tutto schermo: scegli un’app":::

7. Scegliere una delle seguenti opzioni per la modalità di visualizzazione di Microsoft Edge durante l'esecuzione in modalità tutto schermo:

   - Segnaletica digitale/interattiva - Visualizza un sito specifico in modalità a schermo intero, con Microsoft Edge.
   - Browser pubblico - Esegue una versione multi-scheda limitata di Microsoft Edge.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="Visualizzazione in modalità tutto schermo: segno digitale in modalità a schermo intero":::

8. Seleziona **Avanti**.
9. Digita l'URL da caricare all'avvio del chiosco.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="Modalità tutto schermo: immetti l'URL":::

10. Accetta il valore predefinito di 5 minuti per il tempo di inattività o fornisci un valore personalizzato.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="Modalità tutto schermo: immettere il tempo di inattività":::

11. Fai clic su **Avanti**.
12. Chiudi la finestra **Impostazioni**  per salvare e applicare le tue scelte.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="Modalità tutto schermo: completare la configurazione":::

13. Disconnettiti dal chiosco multimediale ed esegui l'accesso con l'account chiosco locale per convalidare la configurazione.

**Passaggio 3: sviluppare un piano di transizione.** In base alle esigenze di testing e organizzazione, è consigliabile sviluppare un piano di transizione e passare a Microsoft Edge su Chromium prima del termine del supporto per la versione legacy di Microsoft Edge che avverrà il 9 marzo 2021.

## <a name="additional-scenarios-that-require-you-to-recreate-an-existing-kiosk-mode"></a>Altri scenari in cui è necessario ricreare una modalità tutto schermo esistente

Se si aggiorna a Windows 10, versione 20H2, verrà installato Microsoft Edge su Chromium e la versione legacy di Microsoft Edge verrà nascosta. In questa istanza è necessario configurare di nuovo la modalità tutto schermo su Microsoft Edge in Chromium.

## <a name="how-to-get-help"></a>Come ottenere assistenza

La modalità tutto schermo può essere una parte importante dell'attività quotidiana, quindi vogliamo contribuire a semplificare al massimo questa transizione e a evitare interruzioni del servizio. Se la propria azienda ha bisogno di assistenza con la transizione a Microsoft Edge su Croromium:

- Il [supporto](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=a77ee9b7-b6b6-aa08-d7b9-887ebe228207) è disponibile da Microsoft. 
- Anche il [supporto FastTrack](https://www.microsoft.com/fasttrack/microsoft-365/microsoft-edge?rtc=1) è disponibile senza costi aggiuntivi per i clienti con almeno 150 postazioni a pagamento di Windows 10 Enterprise.
- In caso di problemi di compatibilità di siti o app, è disponibile [App Assure](https://www.microsoft.com/en-us/fasttrack/microsoft-365/app-assure).

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Il nuovo Microsoft Edge sostituirà la versione legacy di Microsoft Edge nel rilascio di martedì di aprile degli aggiornamenti di Windows 10](https://techcommunity.microsoft.com/t5/microsoft-365-blog/new-microsoft-edge-to-replace-microsoft-edge-legacy-with-april-s/ba-p/2114224)