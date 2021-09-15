---
title: Supporto e configurazione delle identità in Microsoft Edge
ms.author: avvaid
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Supporto e configurazione delle identità in Microsoft Edge
ms.openlocfilehash: 18b82c3f0c4af0e383dd50266c3d9184c76b23af
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979110"
---
# <a name="microsoft-edge-identity-support-and-configuration"></a>Supporto e configurazione delle identità in Microsoft Edge

In questo articolo viene descritto in che modo Microsoft Edge usa l'identità per supportare funzionalità come la sincronizzazione e l'accesso Single Sign-On (SSO). Microsoft Edge supporta l'accesso con Active Directory Domain Services (AD DS), Azure Active Directory (Azure AD) e gli account Microsoft (MSA). Attualmente Microsoft Edge supporta solo gli account di Azure Active Directory (Azure AD) che appartengono al cloud globale o al cloud sovrano GCC. Stiamo lavorando per aggiungere il supporto per altri cloud sovrani.

> [!NOTE]
> Si applica a Microsoft Edge versione 77 o successiva.

## <a name="browser-sign-in-and-authenticated-features"></a>Accesso al browser e funzionalità autenticate

Microsoft Edge supporta l'accesso al profilo del browser con un account Azure AD, MSA o di dominio. Il tipo di account usato per l'accesso determina quali funzionalità autenticate sono disponibili per l'utente in Microsoft Edge. Nella tabella seguente è riepilogato il supporto delle funzionalità per ogni tipo di account.

| Funzionalità   | Azure AD Premium | Azure AD Free | AD DS locale | MSA     |
|----|------------------|---------------|----------------|---------|
| Sincronizzazione | Sì | No | No | Sì |
| SSO con token di aggiornamento primario | Sì | Sì | No | Sì |
| Accesso SSO facile | Sì | Sì | Sì | N/D |
| Autenticazione integrata di Windows | Sì | Sì | Sì | N/D |
| Pagina Nuova scheda per utenti Enterprise | Richiede O365 |   Richiede O365 | No | N/D |
| Microsoft Search | Richiede O365 | Richiede O365 | No | N/D |

## <a name="how-users-can-sign-into-microsoft-edge"></a>Modalità di accesso a Microsoft Edge

### <a name="automatic-sign-in"></a>Accesso automatico

Microsoft Edge usa l'account predefinito del sistema operativo per accedere automaticamente al browser. A seconda di come è configurato un dispositivo, gli utenti possono accedere in modo automatico a Microsoft Edge usando uno degli approcci seguenti.

- **Il dispositivo è ibrido o aggiunto a AAD:** disponibile in Win10, versione legacy di Windows e nelle versioni server corrispondenti.
L'utente si connette automaticamente con il proprio account di Azure Active Directory.
- **Il dispositivo è aggiunto a un dominio:** disponibile in Win10, versione legacy di Windows e nelle versioni server corrispondenti.
Per impostazione predefinita, l'utente non si connetterà in modo automatico. Se si vuole concedere l'accesso automatico agli utenti con account di dominio, usare i [Criteri ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin). Se si vuole concedere l'accesso automatico agli utenti con gli account di Azure AD, è consigliabile aggiungere i dispositivi in modo ibrido.
- **L'account predefinito per il sistema operativo è di tipo MSA:** Win10 RS3 (versione 1709/Build 10.0.16299) e versioni superiori. Questo scenario è improbabile nei dispositivi aziendali. Tuttavia, se l'account predefinito per il sistema operativo è di tipo MSA, Microsoft Edge accederà automaticamente con l'account MSA.

### <a name="manual-sign-in"></a>Accesso manuale

Se l'utente non si connette in modo automatico a Microsoft Edge, può accedere manualmente a Microsoft Edge durante la prima esperienza di esecuzione, tramite le impostazioni del browser o aprendo il riquadro a comparsa di identità.

### <a name="managing-browser-sign-in"></a>Gestione dell'accesso al browser

Se si vuole gestire l'accesso al browser, è possibile usare i criteri seguenti:

- Assicurarsi che gli utenti abbiano sempre un profilo di lavoro su Microsoft Edge. [Vedere NonRemovableProfileEnabled](./microsoft-edge-policies.md#nonremovableprofileenabled)
- Limitare l'accesso a un insieme di account attendibili. [Vedere RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern)
- Disabilitare o forzare l'accesso al browser. [Vedere BrowserSignin](./microsoft-edge-policies.md#browsersignin)

## <a name="browser-to-web-single-sign-on-sso"></a>Uso del browser per l'accesso Single Sign-On al Web (SSO)

In alcune piattaforme è possibile configurare Microsoft Edge per consentire agli utenti di connettersi automaticamente ai siti Web. Questa opzione consente loro di evitare di immettere ogni volta le credenziali per accedere ai siti Web di lavoro, aumentando la produttività.

### <a name="sso-with-primary-refresh-token-prt"></a>SSO con token di aggiornamento primario

Microsoft Edge include il supporto nativo per l'accesso Single Sign-On basato su token di aggiornamento primario (PRT) e non è necessaria un'estensione. In Windows 10 RS3 e versioni superiori, se un utente ha eseguito l'accesso al proprio profilo del browser, otterrà un accesso Single Sign-On con il meccanismo basato su token di aggiornamento primario ai siti Web che supportano il SSO basato su PRT.

Un token di aggiornamento primario è una chiave Azure AD usata per l'autenticazione nei dispositivi Windows 10, iOS e Android. Consente l'accesso Single Sign-on (SSO) alle applicazioni usate in tali dispositivi. Per altre informazioni, vedi [Che cos'è un token di aggiornamento primario?](/azure/active-directory/devices/concept-primary-refresh-token).

### <a name="seamless-sso"></a>Accesso SSO facile

Così come l'accesso SSO basato su PRT, Microsoft Edge include il supporto nativo per SSO facile che non necessita di un'estensione. In Windows 10 RS3 e versioni superiori, se un utente ha eseguito l'accesso al proprio profilo del browser, otterrà un accesso Single Sign-On con il meccanismo basato su token di aggiornamento primario ai siti Web che supportano il SSO basato su PRT.

L'accesso Single Sign-On facile consente agli utenti di connettersi automaticamente quando si trovano su dispositivi aziendali connessi a una rete aziendale. Quando è abilitato, gli utenti non devono digitare le proprie password per accedere ad Azure AD. In genere non devono nemmeno digitare il nome utente. Per altre informazioni, vedi [Accesso Single Sign-On facile di Active Directory](/azure/active-directory/hybrid/how-to-connect-sso).

### <a name="windows-integrated-authentication-wia"></a>Autenticazione integrata di Windows

Microsoft Edge supporta l'autenticazione integrata Windows per le richieste di autenticazione in una rete interna dell'organizzazione per qualsiasi applicazione che usi un browser per l'autenticazione. Questa opzione è supportata in tutte le versioni di Windows 10 e nelle versioni legacy di Windows. Per impostazione predefinita, Microsoft Edge usa l'area Intranet come elenco di indirizzi consentiti per WIA. In alternativa, è possibile personalizzare l'elenco dei server abilitati per l'autenticazione integrata tramite il criterio [AuthServerAllowlist](./microsoft-edge-policies.md#authserverallowlist) . In macOS questo criterio è necessario per abilitare l'autenticazione integrata.

Per supportare l'accesso SSO basato su WIA in Microsoft Edge (versione 77 e successive), potrebbe essere necessario eseguire alcune configurazioni lato server. Probabilmente è necessario configurare la proprietà Active Directory Federation Services (AD FS) **WiaSupportedUserAgents** per aggiungere il supporto per la nuova stringa agente utente di Microsoft Edge. Per informazioni su come eseguire questa operazione vedere [Visualizza impostazioni WIASupportedUserAgent](/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#view-wiasupporteduseragent-settings) e [Modificare le impostazioni di WIASupportedUserAgent](/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#change-wiasupporteduseragent-settings). Di seguito è illustrato un esempio della stringa agente utente Microsoft Edge in Windows 10 ed è possibile ottenere altre informazioni sulla [Stringa Microsoft Edge UA in questa posizione](/microsoft-edge/web-platform/user-agent-string). 

L'esempio seguente mostra una stringa agente utente per l'ultima build del canale Dev quando questo articolo è stato pubblicato:<br> `"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3951.0 Safari/537.36 Edg/80.0.334.2"`

Per i servizi che richiedono la delega delle credenziali di negoziazione, Microsoft Edge supporta la delega vincolata tramite il criterio [AuthNegotiateDelegateAllowlist](./microsoft-edge-policies.md#authnegotiatedelegateallowlist) .

## <a name="additional-authentication-concepts"></a>Concetti di autenticazione aggiuntivi

### <a name="proactive-authentication"></a>Autenticazione proattiva

L'autenticazione proattiva è un'ottimizzazione tramite il browser dell'accesso SSO al sito Web che carica l'autenticazione frontale in determinati siti Web dei proprietari. Questa operazione migliora le prestazioni della barra degli indirizzi se l'utente usa Bing come motore di ricerca. In questo modo gli utenti avranno i risultati della ricerca personalizzati e di Microsoft Search for Business (MSB). Inoltre, consente di abilitare l'autenticazione per i servizi principali, ad esempio la pagina Nuova scheda di Office. È possibile gestire la funzionalità tramite i [Criteri ProactiveAuthEnabled]( /deployedge/microsoft-edge-policies#proactiveauthenabled).

### <a name="windows-hello-credui-for-ntlm-authentication"></a>Windows Hello CredUI per l'autenticazione NTLM

Quando un sito Web consente agli utenti di connettersi tramite NTLM o i meccanismi Negotiate e SSO non è disponibile, offriamo agli utenti un'esperienza in cui possono condividere le credenziali del sistema operativo con il sito Web per soddisfare il test di autenticazione tramite Windows Hello CredUi. Questo flusso di accesso viene visualizzato solo dagli utenti di Windows 10 che non si connettono tramite Single Sign-On durante un test NTLM o Negotiate.

### <a name="sign-in-automatically-using-saved-passwords"></a>Accesso automatico tramite le password salvate

Se un utente salva le password in Microsoft Edge, può abilitare una funzionalità che gli consente di accedere in modo automatico ai siti Web di cui sono state salvate le credenziali. Gli utenti possono attivare e disattivare questa funzionalità spostandosi in *edge://settings/passwords*. Se si vuole configurare questa funzionalità, è possibile usare i [Criteri di per la gestione delle password](./microsoft-edge-policies.md#password-manager-and-protection).

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: Microsoft Edge e identità](microsoft-edge-video-identity.md)
- [Gestione delle identità e degli accessi](https://www.microsoft.com/security/technology/identity-access-management)
- [Piattaforma di identità](https://developer.microsoft.com/identity)
- [Quattro passaggi per una solida base di identità con Azure Active Directory](/azure/active-directory/hybrid/four-steps)