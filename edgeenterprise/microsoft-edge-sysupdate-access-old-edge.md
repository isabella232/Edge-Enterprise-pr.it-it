---
title: Accedere alla versione precedente di Microsoft Edge
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Scopri come accedere alla versione legacy di Microsoft Edge.
ms.openlocfilehash: b521ab9ea093b62db7268e6bf2f4d656b3dc8d4b
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447090"
---
# <a name="access-microsoft-edge-legacy-after-installing-the-new-version-of-microsoft-edge"></a>Accedere a Microsoft Edge Legacy dopo l'installazione della nuova versione di Microsoft Edge

Microsoft Edge Legacy smetterà di ricevere gli aggiornamenti per la sicurezza il 9 marzo 2021. È possibile accedere a Microsoft Edge legacy fino al 13 aprile. Per altre informazioni, Vedi [post di Blog](https://aka.ms/EdgeLegacyEOS)del team Microsoft Edge Product.

> [!NOTE]
> Questo articolo si applica al [canale Stable](microsoft-edge-channels.md) di Microsoft Edge.

Anche se la maggior parte delle organizzazioni vorrà sostituire la versione legacy di Microsoft Edge con la nuova versione, esistono alcune situazioni in cui gli utenti avranno bisogno di accedere a entrambe le versioni. Ad esempio:

- personale dell'helpdesk e del supporto, che interagisce con gli utenti che usano una o entrambe le versioni di Microsoft Edge.
- Sviluppatori che supportano i clienti che usano una o entrambe le versioni di Microsoft Edge.

> [!IMPORTANT]
> Non si consiglia l'esecuzione della Versione legacy di Microsoft Edge in modalità affiancata alla nuova versione di Microsoft Edge per l'uso in produzione. Questa configurazione dovrebbe essere usata solo in casi specifici in cui è necessario eseguire test con entrambe le versioni del browser.
>
> Il supporto per l'app desktop della Versione legacy di Microsoft Edge terminerà il 9 marzo 2021 in favore del nuovo Microsoft Edge. Ciò significa che la Versione legacy di Microsoft Edge non riceverà gli aggiornamenti della sicurezza dopo tale data. Questa modifica è applicabile a tutte le esperienze eseguite nell'app desktop della Versione legacy di Microsoft Edge. [Ulteriori informazioni](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).

## <a name="before-you-begin"></a>Prima di iniziare
> [!NOTE]
> A partire da Windows 10 versione 20H2 la versione legacy di Microsoft Edge non è più disponibile. A partire da questa versione di Windows 10, l'esperienza affiancata non è supportata.

Le procedure illustrate in questo articolo si applicano ai sistemi che sono stati aggiornati con gli ultimi aggiornamenti della sicurezza. Quando verrà installata la nuova versione di Microsoft Edge, la versione precedente (Microsoft Edge Legacy) verrà nascosta. Per impostazione predefinita, tutti i tentativi di avviare la versione precedente reindirizzeranno l'utente alla versione installata di recente di Microsoft Edge. Questo articolo descrive come si può continuare a usare la versione legacy di Microsoft Edge dopo l'installazione di Microsoft Edge.

## <a name="quickstart-side-by-side-experience-with-microsoft-edge-beta-channel-and-microsoft-edge-legacy"></a>Guida introduttiva: Esperienza affiancata con il canale beta di Microsoft Edge e la Versione legacy di Microsoft Edge

Prima di usare le istruzioni dettagliate di questo articolo, tenere presente che i due passaggi seguenti consentono agli utenti di eseguire la Versione legacy di Microsoft Edge e il [canale beta](microsoft-edge-channels.md) di Microsoft Edge in modalità affiancata.

1. Impedisci l'installazione automatica del canale Stable di Microsoft Edge da [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq).
2. Installare il [canale Beta](https://www.microsoft.com/edge/business/download) della nuova versione di Microsoft Edge.

   > [!NOTE]
   > Leggere [Altre informazioni](#additional-information) per informazioni sulle impostazioni della chiave del Registro di sistema.

Questa soluzione affiancata è meno complessa e richiede meno gestione rispetto alla soluzione dettagliata descritta in questo articolo. Tuttavia, sarà necessario eseguire il canale beta al posto del canale stabile.

## <a name="side-by-side-experience-with-microsoft-edge-stable-channel-and-microsoft-edge-legacy"></a>Esperienza affiancata con il canale stabile di Microsoft Edge e la Versione legacy di Microsoft Edge

Installando il canale Stable della versione successiva di Microsoft Edge a livello di sistema, la versione corrente (Microsoft Edge Legacy) verrà nascosta. Se si vuole permettere agli utenti di vedere entrambe le versioni di Microsoft Edge affiancate in Windows, è possibile abilitare questa esperienza impostando il criterio di gruppo **Consenti esperienza browser Microsoft Edge affiancata** su **Abilitato**.

Questo criterio di gruppo è documentato [qui](./microsoft-edge-update-policies.md#allowsxs)

### <a name="to-set-up-the-side-by-side-browser-experience-policy"></a>Per configurare il criterio dell'esperienza browser affiancata:

1. Installare le definizioni dei criteri da [Microsoft Edge for Business](https://www.microsoft.com/edge/business/download).

   - Selezionare il canale, la build e la piattaforma da usare e quindi fare clic sull'opzione per scaricare i file dei criteri.
   - Estrarre i file compressi.
   - Copia msedge.admx e msedgeupdate.admx nella directory `C:\Windows\PolicyDefinitions`.
   - Copiare msedge.adml and msedgeupdate.adml (dalla directory della lingua/delle impostazioni locali appropriata) alla directory `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]`.

2. Apri l'editor Criteri di gruppo (gpedit.msc).
3. In **Configurazione computer** vai a *Modelli amministrativi > Microsoft Edge Update > Applicazioni*.

    > [!NOTE]
    > Se la cartella *Microsoft Edge Update* non è visualizzata, verificare che il passaggio 1 sia stato completato correttamente.

4. In **Applicazioni** fai doppio clic su "Consenti esperienza browser Microsoft Edge affiancata". Vedi le nostre [indicazioni sulle procedure consigliate](#best-practice-guidance) prima di continuare con il passaggio successivo.

    > [!NOTE]
    > Per impostazione predefinita, questo criterio di gruppo è impostato su "Non configurato", il che comporta la scomparsa di Microsoft Edge Legacy quando viene installata la nuova versione di Microsoft Edge.

5. Seleziona **Abilitato**, quindi scegli **OK**.  

Abilitando questo criterio, la chiave del Registro di sistema seguente verrà impostata su' 00000001':

- Chiave: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- Nome: `Allowsxs`
- Tipo valore: `'REG_DWORD'`

#### <a name="best-practice-guidance"></a>Indicazioni sulle procedure consigliate

Per un'esperienza ottimale, il criterio **Consenti esperienza browser Microsoft Edge affiancata** dovrà essere abilitato prima che la nuova versione di Microsoft Edge sia distribuita nei dispositivi degli utenti.

Se i criteri di gruppo vengono abilitati dopo la distribuzione di Microsoft Edge, sono presenti gli effetti collaterali e le azioni necessarie seguenti:

1. **Consenti esperienza browser Microsoft Edge affiancata** non avrà effetto finché non verrà eseguito di nuovo il programma di installazione per la nuova versione di Microsoft Edge.

   > [!NOTE]
   > Il programma di installazione può essere eseguito direttamente o automaticamente quando viene aggiornata la nuova versione di Microsoft Edge.

2. Microsoft Edge Legacy dovrà essere aggiunto di nuovo a Start o alla Barra delle applicazioni perché la migrazione della scelta viene eseguita quando viene distribuita la nuova versione di Microsoft Edge.
3. I siti aggiunti a Start o alla Barra delle applicazioni per Microsoft Edge Legacy verranno migrati alla nuova versione di Microsoft Edge.

## <a name="additional-information"></a>Altre informazioni

Dopo che i sistemi sono stati completamente aggiornati e viene installato il canale Stable della versione successiva di Microsoft Edge, viene impostata la seguente chiave del registro di sistema con relativo valore:

- Chiave: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- Valore chiave: `BrowserReplacement`

  > [!IMPORTANT]
  > Questa chiave è sovrascritta ogni volta che viene aggiornato il canale Microsoft Edge Stable. Come procedura consigliata, ti suggeriamo di NON eliminare questa chiave per consentire agli utenti di accedere a entrambe le versioni di Microsoft Edge.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Aggiornamenti di Windows per supportare Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md)