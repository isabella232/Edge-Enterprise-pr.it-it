---
title: Configurare i criteri della modalità IE
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Configurare i criteri della modalità IE
ms.openlocfilehash: 7ca8dffb0bc20acf954cf0f272f3894b39355846
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980125"
---
# <a name="configure-ie-mode-policies"></a>Configurare i criteri della modalità IE

>[!Note]
> L'applicazione desktop di Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto dal 15 giugno 2022, per un elenco degli elementi nell'ambito, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. [Altre informazioni sono disponibili qui](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Questo articolo spiega come configurare i criteri della modalità IE.

> [!NOTE]
> Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.

La configurazione della modalità IE richiede tre passaggi:

1. [Configurare l'integrazione Internet Explorer](#configure-internet-explorer-integration)
2. [Reindirizzare i siti da Microsoft Edge alla modalità IE](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. (Facoltativo) [Reindirizzare i siti da IE a Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)

    1. Se si desidera disabilitare l'app IE11, seguire i passaggi descritti in [Disabilitare Internet Explorer 11](/deployedge/edge-ie-disable-ie11)
    2. In caso contrario, seguire i passaggi rimanenti in [Reindirizzare i siti da IE a Microsoft Edge](/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)

> [!NOTE]
> I criteri per abilitare la modalità Internet Explorer possono essere configurati tramite Intune. Per altre informazioni, vedere [Aggiungere Microsoft Edge a Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) e [Configurare i criteri Microsoft Edge con Microsoft Intune](./configure-edge-with-intune.md).

## <a name="configure-internet-explorer-integration"></a>Configurare l'integrazione Internet Explorer

È possibile configurare Internet Explorer in modo che venga aperto direttamente all'interno di Microsoft Edge (modalità IE). È anche possibile configurare Internet Explorer in modo che venga aperto con una finestra autonoma di Internet Explorer 11. La maggior parte degli utenti preferisce l'opzione che consente di aprire i siti direttamente all'interno di Microsoft Edge in modalità IE.

### <a name="enable-internet-explorer-integration-using-group-policy"></a>Abilitare l'integrazione Internet Explorer con Criteri di gruppo

1. Scarica e usa il [modello di criteri di Microsoft Edge](https://www.microsoft.com/en-us/edge/business/download) più recente.
2. Apri Editor Criteri di gruppo.
3. Fai clic su **Configurazione utente/Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.
4. Fai doppio clic su **Configura integrazione Internet Explorer**.
5. Seleziona **Attivata**.
6. In **Opzioni** impostare il valore del menu a discesa su
   -  **Modalità Internet Explorer** se si vuole che i siti vengano aperti in modalità IE su Microsoft Edge
   -  **Internet Explorer 11** se vuoi che i siti siano aperti in una finestra autonoma di Internet Explorer 11 (questa opzione non sarà supportata dopo il 15 giugno 2022 quando l'applicazione desktop di Internet Explorer 11 verrà ritirata e non sarà più supportata.  Dopo il 15 giugno 2022 quando Internet Explorer 11 non sarà più disponibile, questa opzione avrà lo stesso comportamento dell'opzione modalità **Internet Explorer.**  
   -  **Nessuno** se si desidera impedire agli utenti di configurare la modalità Internet Explorer tramite edge://flags o la riga di comando

   > [!NOTE]
   > Se si impostano i criteri su **Disabilitato** la modalità Internet Explorer è disabilitata in base ai criteri, ma può essere impostata tramite edge://flags o le opzioni della riga di comando.
7. Fai clic su **OK** o su **Applica** per salvare questa impostazione.

## <a name="redirect-sites-from-microsoft-edge-to-ie-mode"></a>Reindirizzare i siti da Microsoft Edge alla modalità IE

Sono disponibili due opzioni per identificare i siti che devono essere aperti in modalità IE:

- (Consigliato) [Configurare i siti nell'elenco di siti in modalità Enterprise](#configure-sites-on-the-enterprise-site-list)
- [Configurare tutti i siti Intranet](#configure-all-intranet-sites)

### <a name="configure-sites-on-the-enterprise-site-list"></a>Configurare i siti nell'elenco di siti in modalità Enterprise

Puoi usare i seguenti criteri di gruppo per configurare siti specifici da aprire in modalità Internet Explorer:

- [Usa elenco siti Web di Internet Explorer modalità Enterprise](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)
- [Configura elenco siti modalità Enterprise](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, versione 78 o successiva)<br/>Questi criteri consentono di creare un elenco di siti in modalità Enterprise separati per Microsoft Edge. L'abilitazione di questo criterio sovrascrive le impostazioni nel criterio "Usa elenco siti Web di Internet Explorer modalità Enterprise", purché "Configura integrazione Internet Explorer" sia abilitato. La disabilitazione o la configurazione di questo criterio non influisce sul comportamento predefinito del criterio "Configura integrazione Internet Explorer".
    > [!NOTE]
    > Non è obbligatorio configurare il criterio di Microsoft Edge. Molte organizzazioni usano questo criterio come override per indirizzare l'elenco di siti corrente a tutti gli utenti con il criterio di IE e per inoltrare più facilmente una versione aggiornata agli utenti pilota con il criterio di Microsoft Edge.

Per ulteriori informazioni sugli elenchi Enterprise, vedere [Use the Enterprise Site List Manager](/deployedge/edge-ie-mode-site-list-manager).


### <a name="configure-using-the-use-the-enterprise-mode-ie-website-list-policy"></a>Configurare tramite il criterio Usa elenco siti Web di Internet Explorer modalità Enterprise

La modalità IE può usare il criterio esistente configurando l'elenco di siti in modalità Enterprise per Internet Explorer, che consente di creare e gestire un unico elenco.

1. Creare o usare nuovamente un file XML dell'elenco di siti
    1. Tutti i siti che contengono l'elemento _\<open-in\>IE11\</open-in\>_ ora si apriranno in modalità di Internet Explorer.
2. Apri Editor Criteri di gruppo.
3. Fai clic su **Configurazione utente/Configurazione computer** > **Modelli amministrativi** > **Componenti di Windows** > **Internet Explorer**.
4. Fai doppio clic su **Usa elenco siti Web di Internet Explorer modalità Enterprise**.
5. Seleziona **Attivata**.
6. In **Opzioni**, digita il percorso dell'elenco di siti Web. Puoi usare uno dei percorsi seguenti:
    - Percorso HTTPS: **https**:**//iemode/sites.xml** (scelta consigliata)
    - File di rete locale: **\\\network\shares\sites.xml**
    - File locale: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.

### <a name="configure-using-the-configure-the-enterprise-mode-site-list-policy"></a>Configurare tramite il criterio Configura elenco siti modalità Enterprise

È anche possibile configurare la modalità IE con un criterio separato per Microsoft Edge. Questo criterio aggiuntivo consente di eseguire l'override dell'elenco di siti IE. Ad esempio, alcune organizzazioni indirizzano l'elenco di siti di produzione a tutti gli utenti. È quindi possibile distribuire l'elenco di siti pilota a un piccolo gruppo di utenti con questo criterio.

1. Creare o usare nuovamente un file XML dell'elenco di siti
    1. Tutti i siti che contengono l'elemento _\<open-in\>IE11\</open-in\>_ ora si apriranno in modalità di Internet Explorer.
2. Apri Editor Criteri di gruppo.
3. Fai clic su **Configurazione utente/Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.
4. Fai doppio clic su **Configura elenco siti modalità Enterprise**.
5. Seleziona **Attivata**.
6. In **Opzioni**, digita il percorso dell'elenco di siti Web. Puoi usare uno dei percorsi seguenti:
    - Percorso HTTPS: **https**:**//iemode/sites.xml** (scelta consigliata) <!--Trying to keep this from being an active link in MD -->
    - File di rete locale: **\\\network\shares\sites.xml**
    - File locale: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.

### <a name="configure-all-intranet-sites"></a>Configurare tutti i siti Intranet

La modalità IE può essere configurata come tutti i siti nella zona dell'area Intranet locale. È possibile rimuovere singoli siti dalla modalità IE con un elenco di siti in modalità Enterprise.

>[!NOTE]
>
> L'area Intranet locale contiene siti aggiunti esplicitamente, ma è anche possibile assegnare i siti a questa area usando l'euristica. Possono essere inclusi nomi host senza punto (ad esempio, **https**:**//payroll**) e i siti che lo script di configurazione del proxy configura per ignorare il proxy. Se una parte esterna controlla il DNS o il proxy, potrebbe forzare i siti Web in modalità IE.

1. Aprire l'Editor Criteri di gruppo locali.
2. Fai clic su **Configurazione utente/Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.
3. Fai doppio clic su **Invia tutti i siti Intranet a Internet Explorer**.
4. Seleziona **Abilitato** e quindi fai clic su **OK** o su **Applica** per salvare le impostazioni.

## <a name="redirect-sites-from-ie-to-microsoft-edge"></a>Reindirizzare i siti da IE a Microsoft Edge

È possibile impedire agli utenti di usare Internet Explorer per i siti che non lo richiedono. Internet Explorer può reindirizzare automaticamente i siti a Microsoft Edge se non si trovano nell'elenco di siti.

1. Apri Editor Criteri di gruppo.
2. Fai clic su **Configurazione utente/Configurazione computer** > **Strumenti di amministrazione** > **Componenti di Windows** > **Internet Explorer**.
3. Fai doppio clic su **Invia a Microsoft Edge tutti i siti non inclusi nell'elenco siti modalità Enterprise**.
4. Selezionare **Attivato**.
5. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.
6. Fare doppio clic su **Configura quale canale di Microsoft Edge usare per aprire i siti reindirizzati**.
7. Seleziona **Attivata**.
8. In **Opzioni**, selezionare le prime tre scelte per il canale da usare: Internet Explorer reindirizzerà alla scelta con la classificazione più alta che l'utente ha installato sul dispositivo:
   - Canale stabile Microsoft Edge
   - Canale Microsoft Edge Beta versione 77 o successiva
   - Canale Microsoft Edge Dev versione 77 o successiva
   - Canale Microsoft Edge Canary versione 77 o successiva
   - Microsoft Edge versione 45 o precedente
9. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](./edge-ie-mode.md)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
