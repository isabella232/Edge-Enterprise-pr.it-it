---
title: Configurare la modalità tutto schermo di Microsoft Edge
ms.author: aguta
author: aguta
manager: srugh
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare la modalità tutto schermo di Microsoft Edge
ms.openlocfilehash: be353a0e13e9234de40296a2e8dcc31b1b800f52
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297472"
---
# Configurare la modalità tutto schermo di Microsoft Edge

In questo articolo viene descritto come configurare le opzioni della modalità tutto schermo di Microsoft Edge che è possibile provare. Verrà anche descritta una roadmap di funzionalità che abbiamo come obiettivo.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 87 o successiva.

## Panoramica

La modalità tutto schermo di Microsoft Edge offre due esperienze di blocco del browser, in modo che le organizzazioni possano creare, gestire e fornire la migliore esperienza ai propri clienti. Sono disponibili le seguenti esperienze di blocco:  

- Esperienza di **segnaletica digitale/interattiva**: mostra un sito specifico in modalità a schermo intero.
- Esperienza di **esplorazione pubblica**: esegue una versione multi-scheda limitata di Microsoft Edge.

Entrambe le esperienze eseguono una sessione di Microsoft Edge in modalità InPrivate, che protegge i dati dell'utente.

## Configurare la modalità tutto schermo di Microsoft Edge

È disponibile un set iniziale di funzionalità della modalità tutto schermo da testare con il canale stabile Microsoft Edge, versione 87. Puoi scaricare l’ultima versione da [Microsoft Edge (canale stabile ufficiale)](https://www.microsoft.com/edge).

### Funzionalità supportate dalla modalità tutto schermo

La tabella seguente elenca le caratteristiche supportate dalla modalità tutto schermo.

|Funzionalità|Segnaletica digitale/interattiva|Esplorazione pubblica|Disponibile con la versione di Microsoft Edge (e versioni successive)|
|-|-|-|-|
|Spostamento InPrivate|S|S|87|
|Reimpostazione in caso di inattività|S|S|87|
|[Barra degli indirizzi di sola lettura](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (criterio) |N|S |87|
|[Eliminare i download all’uscita](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (criterio)  | S|S |87|
|F11 bloccato (entra/esci dalla modalità a schermo intero) | S | S | 87 |
|F12 bloccato (avvia Strumenti di sviluppo) | S | S | 87 |
| Supporto per più schede | N| S| 87|
|Pulsante Termina sessione | N| S| 88|
|Tutti gli URL Microsoft Edge interni sono bloccati, ad eccezione di *edge://downloads* e *edge://print* |N|S|88|
| CTRL+N bloccato (apri una nuova finestra) | S | S | 89 |
| CTRL+T bloccato (apri una nuova scheda) | N | S | 89 |
|Impostazioni e altro (...) mostreranno solo le opzioni obbligatorie  |N |S |89 |

> [!NOTE]
> Man mano che la modalità tutto schermo si evolve, saranno disponibili più funzionalità.

## Usare le funzionalità della modalità tutto schermo

È possibile richiamare le funzionalità della modalità tutto schermo di Microsoft Edge con le seguenti opzioni della riga di comando per Windows 10:

- Segnaletica digitale/interattiva in modalità tutto schermo: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- Esplorazione pubblica in modalità tutto schermo: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### Opzioni aggiuntive della riga di comando

- `--no-first-run` : disabilita la prima esperienza in esecuzione di Microsoft Edge.
- `--kiosk-idle-timeout-minutes` : modifica il tempo (in minuti) trascorso dall'ultima attività dell’utente prima che la modalità tutto schermo di Microsoft Edge reimposti la sessione dell'utente. Sono supportati i seguenti valori:

  - Valori predefiniti
    - Schermo intero - disattivato
    - Esplorazione pubblica - 5 minuti
  - Valori consentiti
    - 0: spegne il timer
    - 1: 1440 minuti per il ripristino del timer di inattività

## Criteri di supporto per la modalità tutto schermo

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

## Microsoft Edge con accesso assegnato

### Chiosco multimediale con app singola

Attualmente, Microsoft Edge supporta un sottogruppo delle stesse modalità tutto schermo della Versione legacy di Microsoft Edge per accesso assegnato con app singola con le seguenti esperienze di blocco: segnaletica digitale/interattiva ed esplorazione pubblica.  

La modalità tutto schermo con accesso assegnato è al momento disponibile per essere testata con l'ultima  [build di Windows 10 Insider Preview](https://insider.windows.com/), versione 20215 o successiva, e con il  [Canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), versione 87.0.644.4 o successiva.

**Come ottengo l'anteprima di Windows Insiders?**

Per installare una build di Windows 10 Insider Preview su PC, seguire le istruzioni in  [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).

### Chiosco con più app

Microsoft Edge può essere eseguito con [accesso assegnato con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) su Windows 10, che è l'equivalente del tipo di modalità tutto schermo per l'esplorazione normale di Microsoft Edge Legacy. Per configurare Microsoft Edge con l'accesso assegnato con più app, segui le istruzioni su come [Configurare un chiosco multimediale con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps). (L'AUMID per il canale stabile Microsoft Edge è **MSEdge**.)

Quando usi Microsoft Edge con accesso assegnato con più app, puoi configurare il chiosco multimediale di Microsoft Edge in modo da utilizzare i [criteri del browser Microsoft Edge](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) per configurare l'esperienza di esplorazione per soddisfare i tuoi requisiti univoci.

### Configurare usando le impostazioni di Windows

Il modo più semplice per configurare uno o due dispositivi in modalità tutto schermo con app singola è tramite le impostazioni di Windows. Usa i seguenti passaggi per configurare un computer in modalità tutto schermo con app singola.

1. Installa l'ultima versione di Windows 10 Insider Preview, versione 20215 o successiva. Segui le istruzioni in [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).
2. Installa l’ultima versione del [canale stabile Microsoft Edge](https://www.microsoft.com/edge), versione 87 o successiva.  Per testare le caratteristiche più recenti, puoi scaricare l’ultima versione del [canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), versione 89 o successiva.

   > [!IMPORTANT]
   > Poiché è richiesta un'installazione a livello di dispositivo, è supportato solo un canale non Canary.

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

## Limitazioni funzionali

Con il rilascio della versione di anteprima della modalità tutto schermo stiamo continuando a migliorare il prodotto e aggiungere nuove funzionalità.

È consigliabile disattivare:

- [StartupBoostEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [Extensions](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## Roadmap

### All'inizio del 2021

Verranno aggiunte le funzionalità e il supporto seguenti:

- Disponibilità generale della modalità tutto schermo di Microsoft Edge con accesso assegnato con app singola su Windows 10 1909 e versioni successive.
- Funzionalità aggiuntive per la parità con la Versione legacy di Microsoft Edge.
- Integrazione con Intune per configurare i dispositivi con l’esperienza utente del profilo in modalità tutto schermo.
- I tasti di scelta rapida aggiuntivi verranno bloccati.
- Limitazione del lancio di altre applicazioni dal browser.

## Vedi anche

- [Configurare chioschi multimediali e firme digitali nelle edizioni desktop di Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [Distribuire la modalità tutto schermo di Microsoft Edge Legacy](https://aka.ms/edgekioskmode)
- [Pianificare la distribuzione di Microsoft Edge](deploy-edge-plan-deployment.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
