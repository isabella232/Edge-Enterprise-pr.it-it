---
title: Estensioni Microsoft Edge per test interno
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 04/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Informazioni su come creare pacchetti e estensioni di Microsoft Edge per test interno nell'organizzazione.
ms.openlocfilehash: 403b6879b15c146f40fa2564da76eae59b2abe88
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618158"
---
# <a name="self-host-microsoft-edge-extensions"></a>Estensioni Microsoft Edge per test interno

Questo articolo fornisce indicazioni di base per creare un pacchetto di un'estensione da ospitare nel tuo negozio web. Include inoltre istruzioni su come distribuire le estensioni ai dispositivi e agli utenti dell'organizzazione.

## <a name="prerequisites"></a>Prerequisiti

Per ospitare autonomamente le proprie estensioni, è necessario fornire servizi di hosting Web personalizzati per le estensioni e i relativi file manifesto.

 I passaggi seguenti presuppongono che tu abbia già creato l'estensione, abbia esperienza con i file XML, abbia una conoscenza approfondita della configurazione di criteri di gruppo e sappia come usare il Registro di sistema di Windows.

## <a name="publish-an-extension"></a>Pubblicare un'estensione

Prima di pubblicare un'estensione, è necessario comprimerla in un file CRX (estensione Chrome). Usa la procedura seguente come guida per la creazione di un pacchetto di un'estensione come file CRX.

1. Nella barra Microsoft Edge indirizzo, vai a *edge://extensions* e attiva **la modalità sviluppatore** se non è già abilitata.
2. In **Estensioni installate**fare clic su **Comprimi estensione** per creare il file CRX.
3. Usa la finestra di dialogo **Comprimi estensione** per trovare la directory con l'origine per l'estensione. Selezionare la directory e quindi fare clic su **Comprimi estensione**.  Verrà creato il file CRX, insieme a un file PEM. Salvare il file PEM perché è necessario per apportare aggiornamenti della versione dell'estensione. La schermata successiva mostra la finestra di dialogo **Comprimi estensione** per l'individuazione della directory radice dell'estensione.

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="Finestra di dialogo di comprimi estensione per trovare il codice sorgente di un'estensione.":::

   > [!IMPORTANT]
   > Archiviare il file PEM in un percorso sicuro perché è la chiave per l'estensione ed è necessario per gli aggiornamenti futuri.

4. Trascinare il file CRX nella finestra delle estensioni e assicurati che sia caricato.
5. Testare l'estensione e prendere nota del campo ID (questo è l'ID CRX) e del numero di versione. Queste informazioni saranno necessarie in un secondo momento. La schermata successiva mostra un'estensione di test con il relativo ID CRX.

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="Esempio di estensione che mostra l'ID CRX":::

6. Upload il file CRX nell'host e prendere nota dell'URL del percorso da cui verrà scaricato. Queste informazioni sono necessarie per il file manifesto XML.
7. Per creare un file XML manifesto con l'ID app/estensione, l'URL di download e la versione, definisci i campi seguenti:  

   - **appid** - ID dell’estensione del passaggio 5
   - **codebase** - Percorso di download per il file CRX del passaggio 6
   - **version** - Versione dell'app/estensione, che deve corrispondere alla versione specificata nel manifesto dell'estensione.

   Il frammento di codice successivo mostra un esempio di file manifesto XML.

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   Per ulteriori informazioni, vedere [Aggiornamento automatico delle estensioni in Microsoft Edge - Sviluppo di Microsoft Edge](/microsoft-edge/extensions-chromium/enterprise/auto-update).

8. Caricare il file XML completato in un percorso da cui è possibile scaricarlo, prendendo nota dell'URL. Questo URL sarà necessario quando installi l'estensione usando criteri di gruppo. Vedere [Distribuire un'estensione ospitata privatamente.](#distribute-a-privately-hosted-extension)

   > [!IMPORTANT]
   > Il percorso di hosting per l'estensione non richiede l'autenticazione. Deve essere accessibile dai dispositivi degli utenti da ovunque possa essere usata.

## <a name="publish-updates-to-an-extension"></a>Pubblicare aggiornamenti in un'estensione

Dopo aver modificato e testato l'estensione aggiornata, ė possibile pubblicarla. Utilizzare la procedura seguente come guida per la pubblicazione di un aggiornamento.

1. Modificare il numero di versione nel file manifest.JSON dell'estensione in un numero superiore utilizzando la sintassi seguente: `"version":"versionString"`. Se ė la "versione":"1.0", puoi eseguire l'aggiornamento a "version":"1.1" o a qualsiasi numero superiore a "1.0".
2. Aggiornare la "versione" di `<updatecheck>` nel file XML in modo che corrisponda al numero inserito nel file manifesto nel passaggio precedente. Ad esempio:<br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. Crea un file CRX che include le nuove modifiche. Passare a *edge://extensions* e abilitare la **modalità sviluppatore**.
4. Fare clic su **Comprimi estensione** e passare alla directory per l'origine dell'estensione.

   > [!IMPORTANT]
   > Utilizzare lo stesso file PEM generato e salvato la prima volta che è stato creato il file CRX. Se non si usa lo stesso file PEM, l'ID app dell'estensione verrà modificato e l'aggiornamento verrà considerato come una nuova estensione.

5. Trascinare il file CRX nella finestra delle estensioni e verificare che sia caricato.
6. Testare l'estensione aggiornata.
7. Sostituire il vecchio file CRX e il file XML con i nuovi file per l'estensione aggiornata.

Le modifiche dell'estensione verranno ritirate durante il successivo ciclo di sincronizzazione dei criteri. Per ulteriori informazioni sull'aggiornamento delle estensioni, vedere: [aggiornamento URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) e [aggiornamento manifesto](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest).

## <a name="distribute-a-privately-hosted-extension"></a>Distribuire un'estensione ospitata privatamente

Puoi condividere il collegamento del percorso in cui è ospitato il file CRX e non appena gli utenti immettono l'URL nel browser, l'estensione verrà scaricata e installata. Gli utenti possono abilitare l'estensione dalla pagina edge://extensions. Per consentire agli utenti di installare estensioni ospitate privatamente, devi aggiungere gli ID CRX di estensione al criterio [ExtensionInstallAllowList.](/deployedge/microsoft-edge-policies#extensioninstallallowlist)

In alternativa, puoi usare i criteri di gruppo [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) per forzare l'installazione di un'estensione nei dispositivi degli utenti.

Puoi applicare questi criteri agli utenti selezionati, ai dispositivi o a entrambi. Tenere presente che gli aggiornamenti dei criteri non sono istantanei e che passerà del tempo prima che le impostazioni dei criteri saranno effettive.

## <a name="see-also"></a>Vedi anche

- [Gestire le estensioni di Microsoft Edge nell'organizzazione](microsoft-edge-manage-extensions.md)
- [Usare i criteri di gruppo per gestire le estensioni di Microsoft Edge](microsoft-edge-manage-extensions-policies.md)
- [Guida dettagliata al criterio ExtensionSettings](microsoft-edge-manage-extensions-ref-guide.md)
- [Domande frequenti sulle estensioni di Microsoft Edge](microsoft-edge-manage-extensions-faq.md)
- [Pagina di destinazione di Microsoft Edge per le aziende](https://aka.ms/EdgeEnterprise)
