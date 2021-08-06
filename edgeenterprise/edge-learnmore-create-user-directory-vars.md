---
title: Creare variabili di directory dei dati utente di Microsoft Edge
ms.author: brianalt
author: AndreaLBarr
manager: srugh
ms.date: 07/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Scopri come creare variabili di directory dei dati utente di Microsoft Edge
ms.openlocfilehash: e314f23334390fa45efa58daefac0730d8b849732fde75aeacffe4a486c50762
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724269"
---
# <a name="create-microsoft-edge-user-data-directory-variables"></a>Creare variabili di directory dei dati utente di Microsoft Edge

Questo articolo spiega come usare le variabili di directory dei dati invece di usare percorsi hardcoded durante la modifica di Microsoft Edge.

>[!NOTE]
>Questo articolo si applica a Microsoft Edge versione 77 o successiva.
## <a name="path-variables"></a>Variabili di percorso

Criteri per la modifica dei percorsi di directory di dati, ad esempio per la configurazione delle variabili di supporto [UserDataDir](microsoft-edge-policies.md#userdatadir) o [DownloadDirectory](microsoft-edge-policies.md#downloaddirectory). Quando si configurano questi criteri, puoi usare le variabili anziché i percorsi hardcoded. Ad esempio, puoi archiviare i dati del profilo nei dati applicazione locali dell'utente in Windows invece che nel percorso predefinito. Imposta il criterio [UserDataDir](microsoft-edge-policies.md#userdatadir) su **${local_app_data}\Edge\Profile**. Nella maggior parte delle installazioni Windows 10, il percorso si risolve in *C:\Utenti\\&lt;Utente-corrente&gt;\AppData\Local\Microsoft\Edge\Profile*.

>[!NOTE]
>Per visualizzare il  **percorso profilo** corrente, aprire la pagina **Informazioni sulla versione** (digitare "edge://version"). Il formato di **Percorso profilo** è il seguente: *C:\Utenti\\&lt;Utente-corrente&gt;\AppData\Local\Microsoft\Edge\User Data\Default*.

### <a name="guidance-for-using-path-variables"></a>Linee guida per l'uso di variabili di percorso

Prima di usare le variabili per i percorsi, vedi le linee guida seguenti.

- Tutti i criteri che coinvolgono i percorsi in cui Microsoft Edge archivia dati diversi sono dipendenti dalla piattaforma. Alcuni di questi criteri sono disponibili solo su piattaforme specifiche, ma altri possono essere usati in tutte le piattaforme.
- Per evitare errori causati da applicazioni a partire da percorsi diversi in occasioni differenti, assicurati che i percorsi siano assoluti.
- Ogni variabile può essere presente una sola volta in un percorso. Per la maggior parte delle variabili, questo è l'unico modo significativo di usarle, perché si risolvono in percorsi assoluti.
- Quasi tutti i criteri creeranno il percorso se non esiste (se possibile nelle circostanze esistenti).
- L'uso di percorsi di rete per alcuni criteri può comportare risultati imprevisti a causa di differenze nel modo in cui i diversi canali/versioni di Microsoft Edge gestiscono la struttura di cartelle.

### <a name="supported-path-variables"></a>Variabili di percorso supportate

Microsoft Edge supporta le variabili di percorso seguenti.

#### <a name="all-platforms"></a>Tutte le piattaforme

| Variabile | Descrizione |
| --- | --- |
| **${user_name}** | Utente che usa Microsoft Edge. Microsoft Edge rispetta i valori SUID (ID utente proprietario impostato in esecuzione). Esempio: *audreysmall* |
| **${machine_name}** | Nome del computer, con possibilmente incluso il nome di dominio. Esempio: *audreysmall* o *audrey.ex.contoso.com* |

#### <a name="windows-only"></a>Solo Windows

| Variabile | Descrizione |
| --- | --- |
| **${documents}** | Cartella Documenti per l'utente corrente. Esempio: *C:\Utenti\Amministratore\Documenti* |
|**${local_app_data}** | Cartella Dati applicazioni per l'utente corrente. Esempio: *C:\Utenti\Amministratore\AppData\Local* |
|**${roaming_app_data}** | Cartella Dati applicazioni di roaming per l'utente corrente. Esempio: *C:\Utenti\Amministratore\AppData\Roaming* |
| **${profile}** | Home directory per l'utente corrente. Esempio: *C:\Utenti\Amministratore* |
| **${global_app_data}** | Cartella Dati applicazioni a livello di sistema. Esempio: *C:\AppData* |
| **${program_files}** | Cartella Programmi per il processo corrente. Questa cartella varia a seconda che si tratti di un processo a 32 bit o a 64 bit. Risoluzione di esempio: *C:\Programmi (x86)* |
| **${windows}** | Cartella di Windows. Esempio: *C:\Windows* |
| **${client_name}** | Nome del PC client connesso a una sessione RDP o Citrix. Questa variabile è vuota se viene usata da una sessione locale. Se viene usata in un percorso, aggiungi un prefisso con un elemento non vuoto. Esempio: *C:\edge_profiles\session_${client_name}* viene risolto in *C:\edge_profiles\session_&lt;ForlocalSessions&gt;* e *C:\edge_profiles\session_&lt;SomePCname&gt;* per le sessioni remote. |
| **${session_name}** | Nome della sessione attiva. Usare tale nome per distinguere più sessioni remote connesse contemporaneamente che usano un singolo profilo utente. Esempio: *WinSta0 per sessioni desktop locali* |

#### <a name="macos-only"></a>Solo macOS

| Variabile | Descrizione |
| --- | --- |
| **${users}** | Cartella in cui sono archiviati i profili degli utenti. Esempio: */Utenti* |
| **${documents}** | Cartella Documenti per l'utente corrente. Esempio: */Utenti/audreysmall/Documenti* |

## <a name="content-license"></a>Licenza dei contenuti

>[!NOTE]
>Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/). La pagina originale è disponibile [qui](https://www.chromium.org/administrators/policy-list-3/user-data-directory-variables).
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br/>Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.
## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
