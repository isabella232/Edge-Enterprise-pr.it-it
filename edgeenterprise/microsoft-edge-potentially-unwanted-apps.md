---
title: Usare Microsoft Edge per la protezione da applicazioni potenzialmente indesiderate
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Usare Microsoft Edge per la protezione da applicazioni potenzialmente indesiderate
ms.openlocfilehash: 68cd87e85408933212c4b25baa01a9ff8d994089
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643102"
---
# <a name="protect-against-potentially-unwanted-applications-puas"></a>Proteggersi da applicazioni potenzialmente indesiderate

Questo articolo spiega come proteggersi da applicazioni potenzialmente indesiderate con Microsoft Edge o con Windows Defender Antivirus.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 80 o successiva.

## <a name="overview"></a>Panoramica

Le applicazioni potenzialmente indesiderate non sono considerate virus o malware, ma queste app potrebbero eseguire azioni sugli endpoint che influiscono negativamente sulle prestazioni o sull'uso di endpoint. Ad esempio, il *software Evasion* tenta attivamente di eludere il rilevamento da parte dei prodotti di sicurezza. Questo tipo di software può aumentare il rischio di contagio della rete con malware effettivi. Con applicazioni potenzialmente indesiderate ci si può riferire anche ad applicazioni considerate di scarsa reputazione.

Per una descrizione dei criteri usati per classificare il software come applicazioni potenzialmente indesiderate, vedere [Applicazioni potenzialmente indesiderate](/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua).

## <a name="protect-against-pua-with-microsoft-edge"></a>Proteggersi dalle applicazioni potenzialmente indesiderate con Microsoft Edge

Microsoft Edge (versione 80.0.361.50 o successiva) blocca il download delle applicazioni potenzialmente indesiderate e gli URL delle risorse associate.

È possibile configurare la protezione abilitando la funzionalità **Blocca app potenzialmente indesiderate** di Microsoft Edge.

> [!NOTE]
> Il [post di blog del team di Microsoft Edge](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/) descrive questa nuova funzionalità e spiega come gestire un'app etichettata in modo non corretto o segnalare un'app come indesiderata.

### <a name="to-enable-pua-protection"></a>Per abilitare la protezione da applicazioni potenzialmente indesiderate:

1. Aprire **Impostazioni** nel browser.
2. Selezionare **Privacy e servizi**.
3. Nella sezione **Servizi** verificare che l'opzione **Microsoft Defender SmartScreen** sia attivata. In caso contrario, attivare Microsoft Defender SmartScreen. L'esempio nella schermata seguente mostra che il browser è gestito dall'organizzazione e che Microsoft Defender SmartScreen è attivato.

   ![Attivare la protezione da applicazioni potenzialmente indesiderate di Microsoft Edge in Impostazioni](./media/microsoft-edge-potentially-unwanted-apps/security-pua-setup.png)

4. Nella sezione **Servizi** usare l'interruttore mostrato nella schermata precedente per attivare **Blocca app potenzialmente indesiderate**.

   > [!TIP]
   > È possibile esplorare in modo sicuro la funzionalità di blocco degli URL della protezione da applicazioni potenzialmente indesiderate provandola in una delle [pagine demo](https://demo.smartscreen.msft.net/) di Windows Defender SmartScreen.

Se Microsoft Edge rileva un'applicazione potenzialmente indesiderata, verrà visualizzato un messaggio simile a quello illustrato nella schermata seguente.

   ![Messaggio di avviso di applicazioni potenzialmente indesiderate di Microsoft Edge](./media/microsoft-edge-potentially-unwanted-apps/security-pua-msg.png)

### <a name="to-block-against-pua-associated-urls"></a>Per bloccare gli URL associati alle applicazioni potenzialmente indesiderate

Dopo aver attivato la protezione da applicazioni potenzialmente indesiderate in Microsoft Edge, Windows Defender SmartScreen garantirà la protezione dagli URL associati alle applicazioni potenzialmente indesiderate.

Esistono diversi modi in cui gli amministratori possono configurare l'uso di Microsoft Edge e Windows Defender SmartScreen per proteggere gli utenti dagli URL associati alle applicazioni potenzialmente indesiderate. Per altre informazioni, vedi:

- [Configurare le impostazioni dei criteri di Microsoft Edge in Windows](./configure-microsoft-edge.md)
- [Impostazioni di SmartScreen](./microsoft-edge-policies.md#smartscreen-settings)
- [Criterio SmartScreenPuaEnabled](./microsoft-edge-policies.md#smartscreenpuaenabled)
- [Configura Windows Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)

Gli amministratori possono anche personalizzare l'elenco di elementi bloccati di Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP). È possibile usare il portale di Microsoft Defender ATP per [creare e gestire gli indicatori per IP e URL](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview).

## <a name="protect-against-pua-with-windows-defender-antivirus"></a>Proteggersi da applicazioni potenzialmente indesiderate con Windows Defender Antivirus

L'articolo [Rilevare e bloccare le applicazioni potenzialmente indesiderate](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus) descrive anche come configurare Windows Defender Antivirus per abilitare la protezione da applicazioni potenzialmente indesiderate. È possibile configurare la protezione con una delle opzioni seguenti:

- [Microsoft Intune](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-intune-to-configure-pua-protection)
- [Microsoft Endpoint Configuration Manager](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-configuration-manager-to-configure-pua-protection)
- [Criteri di gruppo](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-group-policy-to-configure-pua-protection)
- [Cmdlet PowerShell](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-powershell-cmdlets-to-configure-pua-protection)

Quando Windows Defender rileva un file di un'applicazione potenzialmente indesiderata su un endpoint, lo mette in quarantena e invia una notifica all'utente, [a meno che le notifiche non siano disabilitate](/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus), nello stesso formato di un normale rilevamento di minacce (preceduta da "applicazioni potenzialmente indesiderate:"). Le minacce rilevate vengono visualizzate anche nell'[elenco di quarantena dell'app Sicurezza di Windows](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history).

### <a name="pua-notifications-and-events"></a>Notifiche ed eventi di applicazioni potenzialmente indesiderate

Un amministratore può visualizzare gli eventi di applicazioni potenzialmente indesiderate in diversi modi:

- Nel Visualizzatore eventi di Windows, ma non in Microsoft Endpoint Configuration Manager o Intune.
- In un messaggio di posta elettronica se le notifiche tramite posta elettronica per i rilevamenti di applicazioni potenzialmente indesiderate sono attivate.
- Nei registri eventi di [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus), in cui un evento di un'applicazione potenzialmente indesiderata viene registrato con l'ID evento 1116 e il messaggio: "La piattaforma antimalware ha rilevato malware o altri software potenzialmente indesiderati".

> [!NOTE]
> Gli utenti vedranno che "*.exe è stato bloccato come app potenzialmente indesiderata da Microsoft Defender SmartScreen".

### <a name="allow-list-an-app"></a>Includere un'app in un elenco di elementi consentiti

Come Microsoft Edge, Windows Defender Antivirus fornisce un modo per consentire i file bloccati per errore o necessari per completare un'attività. Se si verifica questo problema, è possibile includere un file in un elenco di elementi consentiti. Per altre informazioni, vedere [Come configurare Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders) per informazioni su come escludere specifici file o cartelle.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Protezione dalle minacce](/windows/security/threat-protection/index)
- [Configurare la protezione in tempo reale, euristica e comportamentale](/windows/security/threat-protection/windows-defender-antivirus/configure-protection-features-windows-defender-antivirus)
- [Protezione di nuova generazione](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)
- [Standard di sicurezza per Microsoft Edge basato su Chromium, versione 79](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/security-baseline-final-for-chromium-based-microsoft-edge/ba-p/1111863)