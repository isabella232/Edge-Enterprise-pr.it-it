---
title: Configurazione della modalità tutto schermo di Microsoft Edge
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/16/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Informazioni sulle funzionalità della modalità tutto schermo e su come configurare le opzioni della modalità tutto schermo di Microsoft Edge.
ms.openlocfilehash: 516bc004a516b243e52d4128ae47f3ab9d7498df
ms.sourcegitcommit: 6a3787dead062e4a0860adbc570229974dcaee07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442486"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a>Configurazione della modalità tutto schermo di Microsoft Edge

In questo articolo viene descritto come configurare le opzioni della modalità tutto schermo di Microsoft Edge che è possibile provare. Verrà anche descritta una roadmap di funzionalità che abbiamo come obiettivo.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 87 o successiva.

> [!IMPORTANT]
> Richiamare le funzionalità della modalità tutto schermo di Microsoft Edge in Windows 10 usando gli argomenti della riga di comando forniti in [Usare le funzionalità della modalità tutto schermo.](#use-kiosk-mode-features)

## <a name="overview"></a>Panoramica

La modalità tutto schermo di Microsoft Edge offre due esperienze di blocco del browser, in modo che le organizzazioni possano creare, gestire e fornire la migliore esperienza ai propri clienti. Sono disponibili le seguenti esperienze di blocco:  

- Esperienza di **segnaletica digitale/interattiva**: mostra un sito specifico in modalità a schermo intero.
- Esperienza di **esplorazione pubblica**: esegue una versione multi-scheda limitata di Microsoft Edge.

Entrambe le esperienze eseguono una sessione di Microsoft Edge in modalità InPrivate, che protegge i dati dell'utente.

## <a name="set-up-microsoft-edge-kiosk-mode"></a>Configurare la modalità tutto schermo di Microsoft Edge

È disponibile un set iniziale di funzionalità della modalità tutto schermo da testare con il canale stabile Microsoft Edge, versione 87. Puoi scaricare l’ultima versione da [Microsoft Edge (canale stabile ufficiale)](https://www.microsoft.com/edge).

### <a name="kiosk-mode-supported-features"></a>Funzionalità supportate dalla modalità tutto schermo

La tabella seguente elenca le caratteristiche supportate dalla modalità tutto schermo di Microsoft Edge e della versione legacy di Microsoft Edge. Usare questa tabella come guida per la transizione a Microsoft Edge, confrontando il modo in cui tali caratteristiche sono supportate in entrambe le versioni di Microsoft Edge.

|Funzionalità|Segnaletica digitale/interattiva|Esplorazione pubblica|Disponibile con la versione di Microsoft Edge (e versioni successive)|Disponibile con la versione legacy di Microsoft Edge|
|-|-|-|-|-|
|Spostamento InPrivate|S|S|89|S|
|Reimpostazione in caso di inattività|S|S|89|S|
|[Barra degli indirizzi di sola lettura](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (criterio) |N|S |89|N|
|[Eliminare i download all'uscita](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (criterio)  | S|S |89|N|
|F11 bloccato (entra/esci dalla modalità a schermo intero) | S | S | 89 |S|
|F12 bloccato (avvia Strumenti di sviluppo) | S | S | 89 |S|
| Supporto per più schede | N| S| 89|S|
|[Consente il supporto degli URL](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) (criterio)|S|S|89|N|
|[Blocca il supporto degli URL](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) (criterio)|S|S|89|N|
|[Mostra il pulsante Home](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showhomebutton) (criterio)|N|S|89|S|
|[Gestione preferiti](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedfavorites) (criterio)|N|S|89|S|
|[Abilita la stampante](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled) (criterio)|S|S|89|S|
|[Configura l'URL della pagina Nuova scheda](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation) (criterio)|N|S||S|
|Pulsante Termina sessione * | N| S| 89|S|
|Tutti gli URL Microsoft Edge interni sono bloccati, ad eccezione di *edge://downloads* e *edge://print* |N|S|89|S|
| CTRL+N bloccato (apri una nuova finestra) * | S | S | 89 |S|
| CTRL+T bloccato (apri una nuova scheda) |S | N | 89 |S|
|Impostazioni e altro (...) mostreranno solo le opzioni obbligatorie  |S |S |89 |S|
|Limitazione del lancio di altre applicazioni dal browser|S|S|90/91|S|
|Blocco delle impostazioni di stampa dell'interfaccia utente|S|S|90/91|S|
|[Imposta la pagina Nuova scheda come home page](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage) (criterio)|-|-|TBD|S|

> [!NOTE]
> Le funzionalità seguite da "*" sono abilitate solo in uno scenario con una singola app con accesso assegnato.

## <a name="use-kiosk-mode-features"></a>Usare le funzionalità della modalità tutto schermo

È possibile richiamare le funzionalità della modalità tutto schermo di Microsoft Edge con le seguenti opzioni della riga di comando per Windows 10 per Insegna digitale o schermo interattivo e per la navigazione pubblica.

### <a name="kiosk-mode-digitalinteractive-signage"></a>Segnaletica digitale/interattiva in modalità tutto schermo
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a>Esplorazione pubblica in modalità tutto schermo

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a>Opzioni aggiuntive della riga di comando

- **--no-first-run**: disabilita la prima esperienza in esecuzione di Microsoft Edge.

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- **--no-first-run**: modifica il tempo (in minuti) trascorso dall'ultima attività dell’utente prima che la modalità tutto schermo di Microsoft Edge reimposti la sessione dell'utente. Sostituire "Valore" nell'esempio successivo con il numero di minuti.

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   Sono supportati i seguenti "valori":

     - Valori predefiniti (in minuti)
       - Schermo intero - 0 (disattivato)
       - Esplorazione pubblica - 5 minuti
    - Valori consentiti
      - 0: spegne il timer
      - 1: 1440 minuti per il ripristino del timer di inattività


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a>Criteri di supporto per la modalità tutto schermo

Usa uno dei criteri di Microsoft Edge elencati nella tabella di seguito per ottimizzare l'esperienza del chiosco multimediale per il tipo di modalità tutto schermo di Microsoft Edge configurata. Per ulteriori informazioni su questi criteri, vedi [Microsoft Edge - Informazioni di riferimento sui criteri del browser](https://docs.microsoft.com/deployedge/microsoft-edge-policies).

> [!NOTE]
> La configurazione dei criteri non è limitata ai criteri elencati nella tabella di seguito, tuttavia i criteri aggiuntivi devono essere testati per verificare che la funzionalità della modalità tutto schermo non sia influenzata negativamente.

|Criteri di gruppo|Segnaletica digitale/interattiva|App singola di esplorazione pubblica|
|--|--|--|
|[Stampa](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | S|S |
|[HomePageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |N | S|
|[ShowHomeButton](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |N | S|
|[NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |N |S |
|[FavoritesBarEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |N |S |
|[URLAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |S |S |
|[URLBlocklist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |S | S|
|[ManagedSearchEngines](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |N | S|
|[UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |N | S|
|[VerticalTabsAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | N|S |
|[Impostazioni SmartScreen](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |S |S |
|[EdgeCollectionsEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)|S|S|

## <a name="microsoft-edge-with-assigned-access"></a>Microsoft Edge con accesso assegnato

### <a name="single-app-kiosk"></a>Chiosco multimediale con app singola

Attualmente, Microsoft Edge supporta un sottogruppo delle stesse modalità tutto schermo della Versione legacy di Microsoft Edge per accesso assegnato con app singola con le seguenti esperienze di blocco: segnaletica digitale/interattiva ed esplorazione pubblica.  

La modalità tutto schermo di Microsoft Edge con app singola con accesso assegnato è al momento disponibile per essere testata con l'ultima  [build di Windows 10 Insider Preview](https://insider.windows.com/), versione 20215 o successiva, e con il  [Canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), versione 89 o successiva.

**Come ottengo l'anteprima di Windows Insiders?**

Per installare una build di Windows 10 Insider Preview su PC, seguire le istruzioni in  [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).

### <a name="multi-app-kiosk"></a>Chiosco con più app

Microsoft Edge può essere eseguito con [accesso assegnato con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) su Windows 10, che è l'equivalente del tipo di modalità tutto schermo per l'esplorazione normale di Microsoft Edge Legacy. Per configurare Microsoft Edge con l'accesso assegnato con più app, segui le istruzioni su come [Configurare un chiosco multimediale con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps). (L'AUMID per il canale stabile Microsoft Edge è **MSEdge**.)

Quando usi Microsoft Edge con accesso assegnato con più app, puoi configurare il chiosco multimediale di Microsoft Edge in modo da utilizzare i [criteri del browser Microsoft Edge](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) per configurare l'esperienza di esplorazione per soddisfare i tuoi requisiti univoci.

### <a name="configure-using-windows-settings"></a>Configurare usando le impostazioni di Windows

Il modo più semplice per configurare uno o due dispositivi in modalità tutto schermo con app singola è tramite le impostazioni di Windows. Usa i seguenti passaggi per configurare un computer in modalità tutto schermo con app singola.

1. Installa l'ultima versione di Windows 10 Insider Preview, versione 20215 o successiva. Segui le istruzioni in [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).
2. Per testare le caratteristiche più recenti, puoi scaricare l’ultima versione del [canale Microsoft Edge Beta](https://www.microsoftedgeinsider.com/download), versione 89 o successiva.
3. Dal computer di un chiosco multimediale, apri le Impostazioni di Windows e digita "chiosco" nel campo di ricerca. Seleziona  **Configura un chiosco multimediale (accesso assegnato**), mostrato nella schermata successiva per aprire la finestra di dialogo per la creazione del chiosco.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

4. Nella pagina **Configura un chiosco multimediale** , fai clic su  **Inizia**.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="Pagina chiosco multimediale: Introduzione":::

5. Digita un nome per creare un nuovo account per chiosco multimediale o scegli un account esistente dall'elenco a discesa popolato e quindi fai clic su  **Avanti**.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="Modalità tutto schermo: crea un account":::

6. Nella pagina **Scegli un'app chiosco multimediale** , seleziona **Microsoft Edge** e quindi fai clic su  **Avanti**.

   > [!NOTE]
   > Questo si applica solo ai canali Microsoft Edge Dev, Beta e Stable.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="Modalità tutto schermo: scegli un’app":::

7. Scegli una delle seguenti opzioni per la modalità di visualizzazione di Microsoft Edge durante l'esecuzione in modalità tutto schermo:

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

## <a name="functional-limitations"></a>Limitazioni funzionali

Con il rilascio della versione di anteprima della modalità tutto schermo stiamo continuando a migliorare il prodotto e aggiungere nuove funzionalità.

Attualmente non sono supportate le funzionalità seguenti e si consiglia di disattivare:

- [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)
- [IsolateOrigins](https://docs.microsoft.com/deployedge/microsoft-edge-policies#isolateorigins)
- [ManagedFavorites](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedfavorites)
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled)
- [EdgeCollectionsEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)
- [UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)
- [DefaultPopupsSetting](https://docs.microsoft.com/deployedge/microsoft-edge-policies#defaultpopupssetting)
- [StartupBoostEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [Extensions](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)
- [UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)

## <a name="roadmap"></a>Roadmap

### <a name="in-early-2021"></a>All'inizio del 2021

Verranno aggiunte le funzionalità e il supporto seguenti:

- Disponibilità generale della modalità tutto schermo di Microsoft Edge con accesso assegnato con app singola su Windows 10 1909 e versioni successive.
- Funzionalità aggiuntive per la parità con la Versione legacy di Microsoft Edge.
- Integrazione con Intune per configurare i dispositivi con l’esperienza utente del profilo in modalità tutto schermo.
- Limitazione del lancio di altre applicazioni dal browser.
- Blocco delle impostazioni di stampa dell'interfaccia utente.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Pianificare la distribuzione di Microsoft Edge](deploy-edge-plan-deployment.md)
- [Configurare chioschi multimediali e firme digitali nelle edizioni desktop di Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [Pianificare la transizione in modalità tutto schermo](microsoft-edge-kiosk-mode-transition-plan.md)
