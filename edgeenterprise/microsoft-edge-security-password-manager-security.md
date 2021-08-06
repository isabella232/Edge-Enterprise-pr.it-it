---
title: 'Sicurezza dello strumento per la gestione delle password di Microsoft Edge '
ms.author: v-andreabarr
author: AndreaLBarr
manager: collw
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Sicurezza dello strumento per la gestione delle password di Microsoft Edge
ms.openlocfilehash: 41f1b269622e0053703af05f344a2d15e8a4b10e72e9507297b877f8047ccccb
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11727059"
---
# <a name="microsoft-edge-password-manager-security"></a>Sicurezza dello strumento per la gestione delle password di Microsoft Edge 

Nelle domande frequenti in questo articolo viene descritto come lo strumento per la gestione delle password integrato di Microsoft Edge fornisce sicurezza per le password degli utenti.

> [!Note]
>Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="how-are-passwords-stored-in-microsoft-edge-and-how-safe-is-this-approach"></a>Come vengono archiviate le password in Microsoft Edge e quanto è sicuro questo approccio?

Microsoft Edge archivia le password crittografate su disco. Vengono crittografate utilizzando la chiave AES256, e la chiave di crittografia viene salvata in un'area di archiviazione del sistema operativo. Questa tecnica è chiamata crittografia dei dati locali. Sebbene non tutti i dati del browser siano crittografati, i dati sensibili come password, numeri di carte di credito e cookie vengono crittografati quando vengono salvati.

Lo strumento per la gestione delle password di Microsoft Edge consente di crittografare le password in modo che siano accessibili solo quando un utente è connesso al sistema operativo. Anche se un utente malintenzionato dispone di diritti di amministratore o accesso offline e può accedere ai dati archiviati localmente, il sistema è progettato per impedire all'autore dell'attacco di ottenere le password di testo non crittografato di un utente che non è connesso.

Le password di un altro utente possono essere decrittografate se quell'utente è connesso e un utente malintenzionato è entrato in possesso della password dell'utente o ha compromesso il controller di dominio.

### <a name="about-the-encryption-method"></a>Informazioni sul metodo di crittografia

La chiave di crittografia del profilo è protetta utilizzando OSCrypt di Chromium e utilizza le seguenti posizioni di archiviazione del sistema operativo specifiche della piattaforma:

- In Windows, l'area di archiviazione è DPAPI

- Su Mac, l'area di archiviazione è il Keychain

- In Linux, l'area di archiviazione è Gnome Keyring o KWallet

Tutte queste aree di archiviazione crittografano la chiave AES256 utilizzando una chiave accessibile ad alcuni o tutti i processi in esecuzione come utente. Questo vettore di attacco è spesso descritto sui blog come un possibile "exploit" o "vulnerabilità", che è un'interpretazione errata del modello di minaccia e del livello di sicurezza del browser.

Tuttavia, gli attacchi e il malware locali sono al di fuori del modello di minaccia e i dati crittografati sono vulnerabili in queste condizioni. Se il computer è infettato da malware, un utente malintenzionato può ottenere l'accesso decrittografato alle aree di archiviazione del browser. Il codice dell'utente malintenzionato, eseguito come account utente, può eseguire qualsiasi operazione.

## <a name="why-encrypt-data-locally-why-not-store-the-encryption-key-elsewhere-or-make-it-harder-to-obtain"></a>Perché crittografare i dati in locale? Perché non archiviare la chiave di crittografia altrove o rendere più difficile ottenerla?

I browser Internet (incluso Microsoft Edge) non sono dotati di protezione contro tali minacce. Pertanto, il dispositivo è completamente compromesso da malware sul computer in esecuzione per conto dell'utente. Tuttavia, programmi come Microsoft Defender SmartScreen e protezioni a livello di sistema operativo come Windows Defender sono progettati per impedire che il dispositivo venga compromesso.

Sebbene la crittografia dei dati locali non possa proteggere dai malware, è utile in determinati scenari. Ad esempio, se un utente malintenzionato trova un modo per rubare i file dal disco senza essere in grado di eseguire il codice o ruba un laptop non protetto dalla crittografia completa del disco, la crittografia dei dati locali renderà più difficile per l'utente malintenzionato ottenere i dati archiviati.

## <a name="do-you-recommend-storing-passwords-in-microsoft-edge"></a>È consigliabile archiviare le password in Microsoft Edge?

Gli utenti che fanno affidamento sullo strumento per la gestione delle password integrato di Microsoft Edge possono usare password più complesse e univoche perché non hanno bisogno di ricordarle tutte e digitarle con la stessa frequenza. Inoltre, poiché lo strumento per la gestione delle password riempirà automaticamente le password solo nei siti a cui appartengono, è meno probabile che gli utenti cadano in un attacco di phishing.

> [!Note]
>I report di settore mostrano che l'80% degli incidenti online è correlato al phishing e oltre il 37% degli utenti non formati non supera i test di phishing.

Lo strumento per la gestione delle password di Microsoft Edge è conveniente e facilmente distribuito e contribuisce a migliorare la sicurezza. In combinazione con la sincronizzazione, è possibile ottenere tutte le password in tutti i dispositivi ed è facile usare una password diversa per ogni sito Web. È possibile usare password lunghe e complesse che non è necessario ricordare per ogni sito ed evitare di digitare una stringa complessa ogni volta. La comodità dello strumento per la gestione delle password aiuta a ridurre il rischio di cadere vittima di phishing.

Tuttavia, l'utilizzo di uno strumento per la gestione delle password legato all'accesso dell'utente al sistema operativo comporta anche la possibilità da parte di un utente malintenzionato di ottenere immediatamente tutte le password utente memorizzate durante quella sessione. Senza uno strumento per la gestione delle password da cui sottrarre i dati, un utente malintenzionato dovrebbe monitorare le sequenze di tasti o le password inviate.

Per decidere se usare o meno uno strumento per la gestione delle password è necessario valutare i numerosi vantaggi descritti in confronto con la possibilità che l'intero dispositivo venga compromesso. Per la maggior parte dei modelli di minacce, l'uso dello strumento per la gestione delle password di Microsoft Edge è l'opzione consigliata.

> [!Note]
>Se un'azienda è preoccupata del fatto che una password specifica sia stata sottratta o che un sito venga violato a causa della sottrazione di una password, è necessario prendere ulteriori precauzioni. Alcune soluzioni efficaci che consentono di mitigare questo tipo di incidente sono il Single Sign On (SSO) tramite Active Directory, Azure Active Directory o una terza parte. Altre soluzioni includono 2FA (come [MS Authenticator](/azure/active-directory/user-help/user-help-auth-app-download-install)) o  [WebAuthN](https://webauthn.guide/).

## <a name="should-a-password-manager-be-enabled-by-an-organization"></a>Un'organizzazione deve abilitare uno strumento per la gestione delle password?

La risposta semplice e semplice: Sì, bisogna usare lo strumento per la gestione delle password.

Una risposta più completa richiede una conoscenza approfondita del modello di minaccia, poiché i parametri e le opzioni di sicurezza dipendono da diversi modelli di minaccia. Ci sono diversi aspetti importanti da considerare quando si decide se abilitare o strumento per la gestione delle password per la propria organizzazione, inclusi i seguenti:

- Da quale tipo di utenti malintenzionati ci si vuole difendere?

- A che tipo di siti Web gli utenti accedono?

- Gli utenti selezionano password complesse e univoche?

- Gli account degli utenti sono protetti con 2FA?

- Quali tipi di attacchi sono più probabili?

- Come si proteggono i dispositivi aziendali dai malware?

- Qual è la tolleranza personale degli utenti per gli inconvenienti?

- Considerare l'impatto della sincronizzazione dei dati.

È importante tenere presente la sicurezza dei dati utente quando vengono sincronizzati con vari dispositivi utente e la quantità di controllo che l'organizzazione ha sulla sincronizzazione automatica dei dati.

Sincronizzazione dei dati e Microsoft Edge:

- La sincronizzazione dei dati può essere abilitata o disabilitata in base alle esigenze dell'organizzazione.

- Sicurezza dei dati in transito e inattivi nel cloud: tutti i dati sincronizzati vengono crittografati in transito su HTTPS quando vengono trasferiti tra il browser e i server Microsoft. I dati sincronizzati vengono archiviati anche in uno stato crittografato nei server Microsoft. I tipi di dati sensibili, ad esempio indirizzi e password, vengono ulteriormente crittografati nel dispositivo prima di essere sincronizzati. Se si usa un account aziendale o dell'istituto di istruzione, tutti i tipi di dati vengono ulteriormente crittografati prima di essere sincronizzati con Microsoft Information Protection.

## <a name="why-do-microsoft-security-baselines-recommend-disabling-the-password-manager"></a>Perché le linee di base della sicurezza Microsoft consigliano di disabilitare lo strumento per la gestione delle password?

Il team di sicurezza di Microsoft ha valutato l'impatto di un worm che compromette una rete di Enterprise PCS (con conseguente perdita di tutte le credenziali negli strumenti per la gestione delle password di tutti i dispositivi) come più grave del rischio (più probabile ma di impatto inferiore) di attacchi di phishing mirati che compromettono una singola credenziale inserita dall'utente.

Questa valutazione è in discussione e soggetta a modifiche con l'aggiunta di nuove funzionalità di miglioramento della sicurezza in Microsoft Edge.

## <a name="can-malicious-extensions-gain-access-to-passwords"></a>Le estensioni dannose possono accedere alle password?

Un'estensione con il permesso di interagire con una pagina è intrinsecamente in grado di accedere a qualsiasi in quella pagina, inclusa una password compilata automaticamente. Allo stesso modo, un'estensione dannosa può modificare il contenuto dei campi modulo e le richieste/risposte di rete per usare in modo improprio l'autorità del contesto di accesso dell'utente corrente.

Tuttavia, Microsoft Edge fornisce un set completo di criteri che consentono un controllo accurato sulle estensioni installate. L'utilizzo dei criteri nella tabella seguente è necessario per proteggere i dati aziendali.

| Criterio | Didascalia |
|-|-|
|[BlockExternalExtensions](/deployedge/microsoft-edge-policies#blockexternalextensions)|Blocca le estensioni esterne dall'installazione|
|[ExtensionAllowedTypes](/deployedge/microsoft-edge-policies#extensionallowedtypes)|Configura i tipi di estensioni consentiti|
|[ExtensionInstallAllowlist](/deployedge/microsoft-edge-policies#extensioninstallallowlist)|Consente l'installazione di estensioni specifiche|
|[ExtensionInstallBlocklist](/deployedge/microsoft-edge-policies#extensioninstallblocklist)|Controlla le estensioni che non è possibile installare|
|[ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)|Controlla le estensioni installate automaticamente|
|[ExtensionInstallSources](/deployedge/microsoft-edge-policies#extensioninstallsources)|Configura le origini di installazione di script utente ed estensione|
| [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) |Configura le impostazioni di gestione delle estensioni |

## <a name="how-does-the-microsoft-edge-password-manager-compare-with-a-third-party-product"></a>In che modo lo strumento di gestione delle password di Microsoft Edge si confronta con i prodotti di terze parti?

Nella tabella seguente viene confrontato lo strumento di gestione delle password di Microsoft Edge con un prodotto di terze parti.

| Gestione password di terze parti | Strumento per la gestione delle password di Microsoft Edge|
|-|-|
| *Sincronizzazione server*. Alcuni prodotti archiviano le password nel cloud per sincronizzare tutti i dispositivi. Questa funzionalità è utile, ma esiste un rischio se il servizio cloud viene compromesso e i dati vengono esposti. **Osservazioni:**  il rischio viene attenuato con la crittografia delle password nel cloud e l'archiviazione della chiave di crittografia nei dispositivi, in modo che gli utenti malintenzionati non possano accedere alla chiave e alle password.| Esiste un rischio di esposizione al cloud perché le password vengono sincronizzate tra i dispositivi Windows in cui è installato Microsoft Edge. **Osservazioni:**  questo rischio è attenuato dalla procedura di sicurezza dei dati illustrata in questo articolo.|
| *Attendibilità*. È necessario considerare attendibile la terza parte considerando che non stia eseguendo operazioni dannose, ad esempio l'invio delle password a un'altra parte. **Osservazioni:**   Questo rischio può essere attenuato esaminando il codice sorgente (nel caso di prodotti open source) o ritenendo che il fornitore si preoccupa della reputazione e dei ricavi. | **Osservazioni:** Microsoft è un fornitore noto e attendibile con una lunga esperienza nel fornire sicurezza e produttività di livello aziendale, con risorse progettate per proteggere le password in tutto il mondo. |
| *Sicurezza della catena di approvvigionamento*. È difficile verificare se il fornitore disponga di processi sicuri per la catena di approvvigionamento/creazione/rilascio per il codice sorgente. |**Osservazioni:** Microsoft dispone di processi interni affidabili per garantire un rischio minimo per il codice sorgente. |
| *Client o account compromesso.*Se un dispositivo client o un account utente viene compromesso, un utente malintenzionato può ottenere le password. **Osservazioni:** Questo rischio è attenuato per alcuni strumenti per la gestione delle password che richiedono all'utente di immettere una password master non archiviata localmente per decrittografare le password.Una password master è solo una mitigazione parziale, poiché un utente malintenzionato potrebbe leggere le sequenze di tasti e ottenere la password master mentre viene digitata o letta dalla memoria del processo durante la compilazione di un campo modulo. | **Osservazioni:** Microsoft offre protezioni a livello di sistema operativo, come Windows Defender, progettate per garantire che il dispositivo non venga compromesso. Tuttavia, se un dispositivo client viene compromesso, un utente malintenzionato potrebbe essere in grado di decrittografare le password. |

> [!Note]
> I prodotti di terze parti potrebbero fornire protezione da modelli di minacce aggiuntivi, ma ciò è a scapito della complessità o della facilità di utilizzo. Lo strumento di gestione delle password di Microsoft Edge è progettato per fornire una gestione delle password comoda e facile da usare che può essere completamente controllata dagli amministratori IT tramite Criteri di gruppo e non richiede terze parti.

## <a name="why-doesnt-microsoft-offer-a-master-password-to-protect-the-data"></a>Perché Microsoft non offre una password master per proteggere i dati?

Quando le password del browser vengono crittografate su disco, la chiave di crittografia è disponibile per qualsiasi processo nel dispositivo, che include i malware eseguiti localmente. Anche se le password vengono crittografate in un "insieme di credenziali" da una chiave master, verranno decrittografate quando vengono caricate nello spazio di archiviazione del browser e possono essere raccolte dopo aver sbloccato l'insieme di credenziali.

Una funzionalità master password (che autentica l'utente prima di compilare automaticamente i dati) offre un compromesso in termini di praticità per una più ampia mitigazione delle minacce. In particolare, aiuta a ridurre la finestra di esposizione dei dati contro malware latenti o utenti malintenzionati locali. Tuttavia, una password master non è una panacea, e gli utenti malintenzionati locali e il malware dedicato hanno diverse strategie per aggirare la protezione di una password master.

> [!Note]
> Microsoft riconosce il valore nell'autenticazione degli utenti prima del riempimento automatico e questa funzionalità verrà aggiunta in Microsoft Edge in una versione futura.

## <a name="can-using-a-password-manager-impact-my-privacy"></a>L'uso di uno strumento per la gestione delle password può influire sulla privacy?

No, non se vengono adottate misure per proteggere l'accesso alle password salvate.

Esiste un exploit noto utilizzato da alcuni inserzionisti, che usa le password archiviate per identificare e monitorare gli utenti. Per altre informazioni, vedere  [Ad targeters are pulling data from your browser’s password manager](https://www.theverge.com/2017/12/30/16829804/browser-password-manager-adthink-princeton-research). I browser hanno preso misure per ridurre questo  [problema di privacy.](https://bugs.chromium.org/p/chromium/issues/detail?id=798492)La classe PasswordValueGatekeeper può essere utilizzata per limitare l'accesso ai dati del campo password, anche quando il browser è configurato per il riempimento automatico al caricamento.

Questa minaccia di raccolta delle informazioni dell'utente può essere facilmente attenuata abilitando la funzionalità facoltativa edge://flags/#fill-on-account-select. Questa funzionalità consente di aggiungere password a un campo modulo solo dopo che l'utente ha scelto esplicitamente una credenziale, in modo che gli utenti rimangano a conoscenza di chi riceve le password.

## <a name="see-also"></a>Vedere anche

[Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download)

[In che modo Microsoft Edge è più sicuro di Chrome for business su Windows 10](/DeployEdge/ms-edge-security-for-business)
