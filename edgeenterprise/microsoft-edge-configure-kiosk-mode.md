---
title: Configurare la modalità tutto schermo di Microsoft Edge
ms.author: aguta
author: aguta
manager: srugh
ms.date: 09/24/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare la modalità tutto schermo di Microsoft Edge
ms.openlocfilehash: 17852cc7c7e4921a0fbef7d09a3f1c3d3cccf49f
ms.sourcegitcommit: b1285b7745eb41b241d706b401f8ce78fa33b227
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078666"
---
# Configurare la modalità tutto schermo di Microsoft Edge

In questo articolo viene descritto come configurare le opzioni della modalità tutto schermo di Microsoft Edge che è possibile provare. Verrà anche descritta una roadmap di funzionalità che abbiamo come obiettivo.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 87 o successiva.

Per informazioni sulla modalità tutto schermo di Microsoft Edge Legacy (versione 45 e versioni precedenti), vedi [Distribuire la modalità tutto schermo di Microsoft Edge](https://aka.ms/edgekioskmode).

## Panoramica

La modalità tutto schermo di Microsoft Edge offre due esperienze di blocco del browser, in modo che le organizzazioni possano creare, gestire e fornire la migliore esperienza ai propri clienti. Sono disponibili le seguenti esperienze di blocco:  

- L'esperienza di segnaletica digitale/interattiva mostra un sito specifico in modalità a schermo intero.
- L'esperienza di esplorazione pubblica esegue una versione multi-scheda limitata di Microsoft Edge.

Entrambe le esperienze eseguono una sessione di Microsoft Edge in modalità InPrivate, che protegge i dati dell'utente.

## Configurare la modalità tutto schermo di Microsoft Edge  

È ora disponibile un set iniziale di funzionalità della modalità tutto schermo da testare con il Canale Microsoft Edge Canary, versione 87. È possibile scaricare Microsoft Edge Canary dalla pagina [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download).

### Funzionalità della modalità tutto schermo

Sono disponibili le seguenti funzionalità:

- Spostamento InPrivate. Protegge i dati degli utenti eliminando i dati del browser e i download al termine della sessione.
- Criteri per configurare Elimina download all'uscita.
- Reimpostare la sessione utente dopo un determinato periodo di inattività.
- Set iniziale di funzionalità di blocco. Sono disponibili le seguenti funzioni:

  - Menu di scelta rapida del mouse
  - F12 Strumenti di sviluppo
  - F11 Uscita dallo schermo intero (in modalità schermo intero)
  - Blocco del set iniziale di pagine *Edge://*

> [!NOTE]
> Man mano che la modalità tutto schermo si evolve, saranno disponibili più funzionalità.

### Usare le funzionalità della modalità tutto schermo

È possibile richiamare le funzionalità della modalità tutto schermo di Microsoft Edge con le seguenti opzioni della riga di comando per Windows 10:

- Segnaletica digitale/interattiva in modalità tutto schermo: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- Esplorazione pubblica in modalità tutto schermo: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

#### Opzioni aggiuntive della riga di comando

- `--no-first-run` : disabilita la prima esperienza in esecuzione di Microsoft Edge.
- `--kiosk-idle-timeout-minutes` : modifica il tempo (in minuti) trascorso dall'ultima attività dell’utente prima che la modalità tutto schermo di Microsoft Edge reimposti la sessione dell'utente. Sono supportati i seguenti valori:

  - Valori predefiniti
    - Schermo intero - disattivato
    - Esplorazione pubblica - 5 minuti
  - Valori consentiti
    - 0: spegne il timer
    - 1: 1440 minuti per il ripristino del timer di inattività

## Impostare la modalità tutto schermo con accesso assegnato

La modalità tutto schermo di Microsoft Edge con accesso assegnato è al momento disponibile per essere testata con l'ultima [build di Windows 10 Insider Preview](https://insider.windows.com/), versione 20215 o successiva, e con il [Canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), versione 87.0.644.4 o successiva.

**Come ottengo l'anteprima di Windows Insiders?**

Per installare una build di Windows 10 Insider Preview su PC, segui le istruzioni in [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).

### Configurare usando le impostazioni di Windows

Il modo più semplice per configurare uno o due dispositivi in modalità tutto schermo con app singola è tramite le impostazioni di Windows. Usa i seguenti passaggi per configurare un computer in modalità tutto schermo con app singola.

1. Installa l'ultima versione di Windows 10 Insider Preview, versione 20215 o successiva. Segui le istruzioni in [Introduzione alle build di Windows 10 Insider Preview](https://docs.microsoft.com/windows-insider/get-started).
2. Installa l'ultima versione del [canale Microsoft Edge Dev](https://www.microsoftedgeinsider.com/download), 87.0.644.4 o successiva.

   > [!IMPORTANT]
   > Poiché è richiesta un'installazione a livello di dispositivo, è supportato solo un canale non Canary.

3. Dal computer di un chiosco multimediale, apri le Impostazioni di Windows e digita "chiosco" nel campo di ricerca. Seleziona  **Configura un chiosco multimediale (accesso assegnato**), mostrato nella schermata successiva per aprire la finestra di dialogo per la creazione del chiosco.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

4. Nella pagina **Configura un chiosco multimediale** , fai clic su  **Inizia**.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

5. Digita un nome per creare un nuovo account per chiosco multimediale o scegli un account esistente dall'elenco a discesa popolato e quindi fai clic su  **Avanti**.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

6. Nella pagina **Scegli un'app chiosco multimediale** , seleziona **Microsoft Edge** e quindi fai clic su  **Avanti**.

   > [!NOTE]
   > Questo si applica solo ai canali Microsoft Edge Dev, Beta e Stable.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

7. Scegli una delle seguenti opzioni per la modalità di visualizzazione di Microsoft Edge durante l'esecuzione in modalità tutto schermo:

   - Segnaletica digitale/interattiva - Visualizza un sito specifico in modalità a schermo intero, con Microsoft Edge.
   - Browser pubblico - Esegue una versione multi-scheda limitata di Microsoft Edge.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

8. Seleziona **Avanti**.
9. Digita l'URL da caricare all'avvio del chiosco.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

10. Accetta il valore predefinito di 5 minuti per il tempo di inattività o fornisci un valore personalizzato.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="Impostare un chiosco multimediale con accesso assegnato":::

11. Fai clic su **Avanti**.
12. Chiudi la finestra **Impostazioni**  per salvare e applicare le tue scelte.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="Impostare un chiosco multimediale con accesso assegnato" abiliterà solo le opzioni richieste (ad esempio, Stampa, Guida, Feedback e Leggi ad alta voce)":::
  - Pagine di blocco aggiuntive *edge://* (ad esempio, *edge://settings*)
  - Configurazione dell'interfaccia utente delle opzioni di stampa
  - Limitazione di esplorazione dei file solo alla cartella di download.

### All'inizio del 2021

Verranno aggiunte le seguenti funzionalità e supporto:

- Disponibilità generale della modalità tutto schermo di Microsoft Edge con app singola con accesso assegnato su Windows.
- Funzionalità aggiuntive per la parità con la versione legacy di Microsoft Edge.
- Integrazione con Intune per configurare i dispositivi con il profilo in modalità tutto schermo UX.

## Vedere anche

- [Configurare chioschi multimediali e firme digitali nelle edizioni desktop di Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [Distribuire la modalità tutto schermo di Microsoft Edge Legacy](https://aka.ms/edgekioskmode)
- [Pianificare la distribuzione di Microsoft Edge](deploy-edge-plan-deployment.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
