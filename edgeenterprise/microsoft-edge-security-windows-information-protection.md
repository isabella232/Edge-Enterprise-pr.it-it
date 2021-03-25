---
title: Supporto Microsoft Edge per Windows Information Protection
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 04/24/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Supporto Microsoft Edge per Windows Information Protection
ms.openlocfilehash: a9981947462627ae4884f18f4df6accf2ee60f12
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447190"
---
# <a name="microsoft-edge-support-for-windows-information-protection-wip"></a>Supporto Microsoft Edge per Windows Information Protection (WIP)

Questo articolo descrive come Microsoft Edge supporta Windows Information Protection.

> [!NOTE]
> Si applica a Microsoft Edge, versione 81 o successiva.

## <a name="overview"></a>Panoramica

Windows Information Protection (WIP) è una funzionalità di Windows 10 che consente di proteggere i dati aziendali dalla divulgazione non autorizzata o accidentale. Con l'aumento del lavoro in remoto, esiste un rischio maggiore di condivisione dei dati aziendali al di fuori del luogo di lavoro. Questo rischio aumenta quando le attività personali e di lavoro coesistono sui dispositivi aziendali.

Microsoft Edge supporta Windows Information Protection nella protezione dei contenuti in ambiente Web, dove spesso gli utenti condividono e distribuiscono contenuti.

### <a name="system-requirements"></a>Requisiti di sistema

I requisiti seguenti si applicano ai dispositivi che usano Windows Information Protection all'interno dell'azienda:

- Windows 10 versione 1607 o successiva
- Solo SKU dei client Windows.
- Una delle soluzioni di gestione descritte nei [Prerequisiti di Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)

### <a name="windows-information-protection-benefits"></a>Vantaggi di Windows Information Protection

Windows Information Protection offre i vantaggi seguenti:

- L'ovvia separazione tra dati personali e aziendali, senza richiedere ai dipendenti di cambiare ambiente o app.
- Protezione dei dati aggiuntiva per le app line-of-business esistenti senza che risulti necessario aggiornare le app.
- La possibilità di cancellare in remoto i dati aziendali dai dispositivi registrati in Mobile Device Management di Intune, lasciando invariati i dati personali. 
- Report di controllo per il tracciamento dei problemi e per le azioni correttive, ad esempio la formazione sulla conformità per gli utenti.
- Integrazione con il sistema di gestione esistente per configurare, distribuire e gestire Windows Information Protection. Alcuni esempi sono costituiti da Microsoft Intune, Microsoft Endpoint Configuration Manager o il sistema corrente di gestione dei dispositivi mobili.

## <a name="wip-policy-and-protection-modes"></a>Criteri e modalità di protezione di Windows Information Protection

Tramite i criteri, è possibile configurare le quattro modalità di protezione descritte nella tabella seguente. Per altre informazioni, vedere [Modalità di protezione di Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes).

| Modalità | Descrizione |
|------|-------------|
| Blocca | Windows Information Protection controlla se vengono eseguite operazioni di condivisione dei dati non appropriate e impedisce al dipendente di completare l'azione. Questa ricerca può includere la condivisione di dati aziendali in app senza protezione aziendale, oltre alla condivisione di dati aziendali tra app o il tentativo di condivisione all'esterno della rete dell'organizzazione. |
| Consenti sostituzioni | Windows Information Protection controlla se vengono eseguite operazioni di condivisione dei dati non appropriate e segnala ai dipendenti l'esecuzione di operazioni potenzialmente non sicure. Tuttavia, questa modalità di gestione permette al dipendente di ignorare i criteri e condividere comunque i dati, registrando l'azione nel log di controllo. |
| Invisibile all'utente | Windows Information Protection viene eseguito in modo invisibile all'utente, registrando le attività di condivisione dei dati inappropriate, senza arrestare alcuna attività per cui verrebbe chiesta l'interazione del dipendente in modalità Consenti sostituzioni. Le azioni non consentite, come quella di un'app che prova in modo non appropriato ad accedere a una risorsa di rete o a dati protetti da Windows Information Protection, continuano a essere arrestate. |
| Disattivato | Windows Information Protection è disattivato e non esegue alcuna attività di controllo o protezione dei dati. Dopo aver disattivato Windows Information Protection, viene eseguito il tentativo di decrittografare qualsiasi file con tag di Windows Information Protection nelle unità collegate localmente. Le precedenti informazioni su decrittografia e criteri non vengono riapplicate automaticamente riattivando la protezione di Windows Information Protection.
 |

## <a name="wip-features-supported-in-microsoft-edge"></a>Funzionalità di Windows Information Protection in Microsoft Edge

A partire dalla versione 81 di Microsoft Edge, sono supportate le seguenti funzionalità:

- I siti di lavoro verranno contrassegnati da un'icona a forma di ventiquattrore sulla barra degli indirizzi.  
- I file scaricati da una posizione di lavoro vengono crittografati automaticamente.
- Imposizione della modalità automatica/blocco/sostituzione per il caricamento dei file di lavoro in posizioni non di lavoro.  
- Imposizione della modalità automatica/blocco/sostituzione per le operazioni di trascinamento dei file.
- Imposizione della modalità automatica/blocco/sostituzione per le operazioni in Appunti.
- L'esplorazione delle posizioni di lavoro da profili non lavorativi reindirizza automaticamente al profilo di lavoro (associato all'identità di Azure AD).
- La modalità Internet Explorer supporta le funzionalità complete di Windows Information Protection.

## <a name="working-with-wip-in-microsoft-edge"></a>Utilizzo di Windows Information Protection in Microsoft Edge

Dopo aver abilitato il supporto di Windows Information Protection per Microsoft Edge, gli utenti visualizzeranno le modalità di accesso alle informazioni di lavoro. La schermata successiva mostra l'icona a forma di ventiquattrore nella barra degli indirizzi, che indica che è possibile accedere alle informazioni di lavoro tramite il browser.

 ![Indicatore nella barra degli indirizzi per i siti contrassegnati come "lavoro"](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-notify.png)

Microsoft Edge offre agli utenti la possibilità di condividere contenuti protetti in siti Web non approvati. La schermata seguente mostra l'avviso di Microsoft Edge che consente agli utenti di usare i contenuti protetti in siti Web non approvati.

 ![Avviso per la sostituzione del contenuto protetto](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-override.png)

## <a name="configure-policies-to-support-wip"></a>Configurare i criteri per il supporto di Windows Information Protection

L'uso di Windows Information Protection con Microsoft Edge richiede l'esistenza di un profilo di lavoro.

### <a name="ensure-the-presence-of-a-work-profile"></a>Assicurarsi dell'esistenza di un profilo di lavoro

Nei computer collegati con identità ibrida, Microsoft Edge si connette automaticamente con l'account di Azure Active Directory (Azure AD). Per assicurarsi che gli utenti non rimuovano questo profilo necessario per Windows Information Protection, configurare i criteri seguenti:

- [NonRemovableProfileEnabled](./microsoft-edge-policies.md#nonremovableprofileenabled)

> [!NOTE]
> Se l'ambiente in uso non è connesso con identità ibrida, è possibile connetterlo seguendo queste istruzioni: [Pianificare l'implementazione della connessione ibrida di Azure Active Directory](/azure/active-directory/devices/hybrid-azuread-join-plan).

Se la connessione ibrida non è disponibile, è possibile usare gli account di Active Directory locali per consentire a Microsoft Edge di creare automaticamente un profilo di lavoro specifico con gli account di dominio degli utenti. Tenere presente che gli account locali potrebbero non ricevere tutte le funzionalità di Azure Active Directory, ad esempio sincronizzazione nel cloud, Office NTP e così via.

#### <a name="active-directory-ad-accounts"></a>Account di Active Directory

Per gli account di Active Directory, è necessario configurare i criteri seguenti affinché Microsoft Edge crei automaticamente un profilo di lavoro specifico.

- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin)

### <a name="windows-policies-for-wip"></a>Nuovi criteri per Windows Information Protection

È possibile configurare Windows Information Protection tramite i criteri di Windows. Per altre informazioni, vedere [Creare e distribuire criteri di Windows Information Protection tramite Microsoft Intune](/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="how-do-i-resolve-error-code--2147024540"></a>Come posso risolvere il codice di errore 2147024540?

Questo codice di errore corrisponde al seguente errore di Windows Information Protection: *ERROR_EDP_POLICY_DENIES_OPERATION: L'operazione richiesta è stata bloccata dai criteri di Windows Information Protection. Per altre informazioni, contatta l'amministratore di sistema.*

Microsoft Edge mostra questo errore quando l'organizzazione ha abilitato Windows Information Protection (WIP) per consentire solo agli utenti con applicazioni approvate di accedere alle risorse aziendali. In questo caso, poiché Microsoft Edge non è presente nell'elenco delle applicazioni approvate, l'amministratore dovrà aggiornare i criteri di Windows Information Protection per concedere l'accesso a Microsoft Edge.

Lo screenshot seguente mostra il modo in cui viene usato Microsoft Intune per aggiungere Microsoft Edge come app consentita per WIP.

 ![Finestra di dialogo Intune per aggiungere Microsoft Edge come app per WIP](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-exemption.png)

Se non si usa Microsoft Intune, scaricare e applicare l'aggiornamento dei criteri nel file [WIP Enterprise AppLocker Policy](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip).

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise) 
- [Proteggere i dati aziendali tramite Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)