---
title: Configurare Microsoft Edge con la gestione di dispositivi mobili
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 04/06/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare Microsoft Edge con la gestione di dispositivi mobili.
ms.openlocfilehash: a24e6d171707cdc02b6dbecb573e1238f1273426
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617606"
---
# <a name="configure-microsoft-edge-using-mobile-device-management"></a>Configurare Microsoft Edge con la gestione di dispositivi mobili

Questo articolo spiega come configurare Microsoft Edge in Windows 10 con la [gestione di dispositivi mobili (MDM)](/windows/client-management/mdm/) tramite l'[inserimento ADMX](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration). Questo articolo descrive anche:

- Come [creare un valore URI OMA (Open Mobile Alliance Uniform Resource Identifier) per i criteri di Microsoft Edge](#create-an-oma-uri-for-microsoft-edge-policies).
- Come [configurare Microsoft Edge in Intune tramite l'inserimento ADMX e i valori URI OMA personalizzati](#configure-microsoft-edge-in-intune-using-admx-ingestion).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="prerequisites"></a>Prerequisiti

Windows 10, con i requisiti minimi di sistema seguenti:

- Windows 10, versione 1903 con [KB4512941](https://support.microsoft.com/help/4512941/) e [KB4517211](https://support.microsoft.com/help/4517211/) installati
- Windows 10, versione 1809 con [KB4512534](https://support.microsoft.com/help/4512534/) e [KB4520062](https://support.microsoft.com/help/4520062/) installati
- Windows 10, versione 1803 con [KB4512509](https://support.microsoft.com/help/4512509/) e [KB4519978](https://support.microsoft.com/help/4519978) installati
- Windows 10, versione 1709 con [KB4516071](https://support.microsoft.com/help/4516071/) e [KB4520006](https://support.microsoft.com/help/4520006) installati

## <a name="overview"></a>Panoramica

Puoi configurare Microsoft Edge in Windows 10 usando MDM con il provider EMM (Enterprise Mobility Management) o il provider MDM che supporta [l'inserimento ADMX](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).

La configurazione di Microsoft Edge con MDM è un processo in due parti:

1. Inserimento del file ADMX di Microsoft Edge nel provider EMM o MDM. Per istruzioni su come inserire un file ADMX, vedi le istruzioni del provider.

   > [!NOTE]
   > Per Microsoft Intune, vedi [Configurare Microsoft Edge in Intune tramite l'inserimento ADMX](#configure-microsoft-edge-in-intune-using-admx-ingestion).

2. [Creazione di un valore URI OMA per i criteri di Microsoft Edge](#create-an-oma-uri-for-microsoft-edge-policies).

## <a name="create-an-oma-uri-for-microsoft-edge-policies"></a>Creare un valore URI OMA per i criteri di Microsoft Edge

Le sezioni seguenti descrivono come creare il percorso URI OMA e come cercare e definire il valore in formato XML per i criteri di ricerca obbligatori e consigliati per il browser.

Prima di iniziare, scarica il file dei modelli di criteri di Microsoft Edge (MicrosoftEdgePolicyTemplates.cab) nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise) ed estrai il contenuto.

Sono disponibili tre passaggi per definire l'URI OMA:

1. [Creare il percorso URI OMA](#create-the-oma-uri-path)
2. [Specificare il tipo di dati URI OMA](#specify-the-data-type)
3. [Impostare il valore URI OMA](#set-the-value-for-a-browser-policy)

### <a name="create-the-oma-uri-path"></a>Creare il percorso URI OMA

Usa la formula seguente come guida per la creazione dei percorsi URI OMA. <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| Parametro         | Descrizione                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | Usa "Edge" o il nome definito durante l'inserimento del modello amministrativo. Se ad esempio hai usato "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx", devi usare "MicrosoftEdge".<br/><br/> Il nome `<ADMXIngestionName>` deve corrispondere a quello usato quando hai inserito il file ADMX. |
| \<ADMXNamespace>  | "microsoft_edge" o "microsoft_edge_recommended", a seconda che il criterio impostato sia obbligatorio o consigliato. |
| \<ADMXCategory>   | L'elemento "parentCategory" del criterio è definito nel file ADMX. Ometti `<ADMXCategory>` se il criterio non è in gruppo (nessune elemento "parentCategory" definito). |
| \<PolicyName>     | Il nome del criterio è disponibile nell'articolo [Informazioni di riferimento sui criteri del browser](./microsoft-edge-policies.md). |

#### <a name="uri-path-example"></a>Esempio di percorso URI

Per questo esempio, assumi che il nodo `<ADMXIngestName>` sia stato denominato "Edge" e che tu stia impostando un criterio obbligatorio. Il percorso URI sarebbe:<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

Se il criterio non appartiene a un gruppo (ad esempio DiskCacheSize), rimuovi "`~<ADMXCategory>`". Sostituisci `<PolicyName>` con il nome del criterio, DiskCacheSize. Il percorso URI sarebbe:<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

Se il criterio appartiene a un gruppo, segui questa procedura:

1. Apri **msedge.admx** con qualsiasi editor XML.
2. Cerca il nome del criterio che vuoi applicare. Ad esempio, "ExtensionInstallForceList".
3. Usa il valore dell'attributo *ref* dell'elemento *parentCategory*. Ad esempio, "estensioni" da \<parentCategory ref=" Extensions"/>.
4. Sostituisci `<ADMXCategory>` con il valore dell'attributo *ref* per creare il percorso URI. Il percorso URI sarebbe:<br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <a name="specify-the-data-type"></a>Specificare il tipo di dati

Il tipo di dati URI OMA è sempre “String”.

### <a name="set-the-value-for-a-browser-policy"></a>Impostare il valore per un criterio del browser

In questa sezione viene descritto come impostare il valore, in formato XML, per ogni tipo di dati. Vai a [Informazioni di riferimento sui criteri del browser](./microsoft-edge-policies.md) per cercare il tipo di dati del criterio.

> [!NOTE]
> Per i tipi di dati non Boolean, il valore inizia sempre con `<enabled/>`.

#### <a name="boolean-data-type"></a>Tipo di dati Boolean

Per i criteri con tipi Boolean usa `<enabled/>` o `<disabled/>`.

#### <a name="integer-data-type"></a>Tipo di dati Integer

Il valore inizia sempre con l'elemento `<enabled/>` seguito da `<data id="[valueName]" value="[decimal value]"/>`.

Per trovare il nome del valore e il valore decimale per una pagina Nuova scheda, seguire questa procedura:

1. Apri **msedge.admx** con qualsiasi editor XML.
2. Cerca l'elemento `<policy>` in cui l'attributo del nome corrisponde al nome del criterio da impostare. Per "RestoreOnStartup", cerca `name="RestoreOnStartup"`.
3. Nel nodo `<elements>`, trova il valore da impostare.
4. Usa il valore nell'attributo "valueName" nel nodo `<elements>`. Per "RestoreOnStartup" il valore "valueName" è "RestoreOnStartup".
5. Usa il valore nell'attributo "value" nel nodo `<decimal>`. Per "RestoreOnStartup", per aprire la pagina Nuova scheda il valore è "5".

Per aprire la pagina Nuova scheda all'avvio usa:<br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <a name="list-of-strings-data-type"></a>Elenco di tipi di dati stringhe

Il valore inizia sempre con l'elemento `<enabled/>` seguito da `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`.

> [!NOTE]
> Il nome dell'attributo "id=" non è il nome del criterio, anche se nella maggior parte dei casi corrisponde al nome del criterio. Si tratta del valore dell'attributo ID del nodo \<list> presente nel file ADMX.

Per trovare l'elemento listID e definire il valore per bloccare un URL, esegui queste operazioni:

1. Apri **msedge.admx** con qualsiasi editor XML.
2. Cerca l'elemento `<policy>` in cui l'attributo del nome corrisponde al nome del criterio da impostare. Per "URLBlocklist", cerca `name="URLBlocklist"`.
3. Usa il valore dell'attributo "id" dell'elemento `<list> node for [listID]`.
4. L'elemento "value" è un elenco di URL separati da un punto e virgola (;)

Ad esempio, per bloccare l'accesso a `contoso.com` e `https://ssl.server.com`:<br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <a name="dictionary-or-string-data-type"></a>Tipo di dati Dictionary o String

Il valore deve sempre iniziare con l'elemento `<enabled/>` seguito da `<data id="[textID]" value="[string]"/>` .

Per trovare l'elemento textID e definire il valore per impostare le impostazioni locali, esegui queste operazioni:

1. Apri **msedge.admx** con qualsiasi editor XML.
2. Cerca l'elemento `<policy>` in cui l'attributo del nome corrisponde al nome del criterio da impostare. Per "ApplicationLocaleValue" cerca `name="ApplicationLocaleValue"`.
3. Usa il valore dell'attributo "id" del nodo `<text>` per `[textID]`.
4. Imposta l'elemento "value" sul codice relativo alle impostazioni cultura.

Per impostare le impostazioni locali su "es-US" con il criterio "ApplicationLocaleValue":<br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

### <a name="create-the-oma-uri-for-a-recommended-policies"></a>Creare l'URI OMA per un criterio consigliato

La definizione del percorso URI per i criteri consigliati dipende dal criterio che desideri configurare.

#### <a name="to-define-the-uri-path-for-a-recommended-policy"></a>Per definire il percorso URI per un criterio consigliato

Usa la formula del percorso URI (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) e i passaggi seguenti per definire il percorso URI:

1. Apri **msedge.admx** con qualsiasi editor XML.
2. Se il criterio da configurare non è incluso in un gruppo, vai al passaggio 4 e rimuovi `~<ADMXCategory>` dal percorso.
3. Se il criterio da configurare si trova in un gruppo:

   - Per cercare `<ADMXCategory>`, cerca il criterio da impostare. Durante la ricerca, aggiungi "_recommended" al nome del criterio. Ad esempio, una ricerca per "RegisteredProtocolHandlers_recommended" restituisce il risultato seguente:

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - Copia il valore dell'attributo *ref* dall'elemento `<parentCategory>`. Per "ContentSettings", copia "ContentSettings_recommended" da `<parentCategory ref=" ContentSettings_recommended"/>`.
   - Sostituisci `<ADMXCategory>` con il valore dell'attributo *ref* per creare il percorso URI nella formula relativa.

4. `<PolicyName>` è il nome del criterio con il suffisso "_recommended".

#### <a name="oma-uri-path-examples-for-recommended-policies"></a>Esempi di percorso URI OMA per i criteri consigliati

Nella tabella seguente sono riportati alcuni esempi di percorsi URI OMA per i criteri consigliati.

|              Criterio               |             URI OMA                      |
|-----------------------------------|------------------------------------------|
| [RegisteredProtocolHandlers](./microsoft-edge-policies.md#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [PasswordManagerEnabled](./microsoft-edge-policies.md#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [PrintHeaderFooter](./microsoft-edge-policies.md#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [HomePageLocation](./microsoft-edge-policies.md#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [ShowHomeButton](./microsoft-edge-policies.md#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [FavoritesBarEnabled](./microsoft-edge-policies.md#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <a name="oma-uri-examples"></a>Esempi URI OMA

Esempi di URI OMA con il percorso URI, il tipo e un valore di esempio.

#### <a name="boolean-data-type-examples"></a>Esempi di tipi di dati Boolean

*[ShowHomeButton](./microsoft-edge-policies.md#showhomebutton):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: ShowHomeButton                                                       |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| Tipo    | String                                                                               |
| Valore   | `<enabled/>`                                                                          |

*[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: DefaultSearchProviderEnabled                                         |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| Tipo    | String                                                                               |
| Valore   | `<disable/>`                                                                          |

### <a name="integer-data-type-examples"></a>Esempi di tipi di dati Integer

*[AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: AutoImportAtFirstRun                                                 |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| Tipo    | String                                                                               |
| Valore   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*[DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: DefaultImagesSetting                                                 |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| Tipo    | String                                                                               |
| Valore   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*[DiskCacheSize](./microsoft-edge-policies.md#diskcachesize):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: DiskCacheSize                                                        |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| Tipo    | String                                                                               |
| Valore   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <a name="list-of-strings-data-type-examples"></a>Elenco di esempi di tipi di dati String
<!--
*[NotificationsAllowedForUrls](./microsoft-edge-policies.md#NotificationsAllowedForUrls):*

| Field   | Value                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Name    | Microsoft Edge: NotificationsAllowedForUrls                                          |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/NotificationsAllowedForUrls`    |
| Type    | String                                                                               |
| Value   | `<enabled/><data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com"/>`<br>For multiple list items: `<data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com;[*.]contoso.edu"/>`                           |
-->
*[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: RestoreOnStartupURLS                                                 |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| Tipo    | String                                                                               |
| Valore   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br>Per elementi di più elenchi: `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: ExtensionInstallForcelist                                            |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| Tipo    | String                                                                               |
| Valore   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <a name="dictionary-and-string-data-type-example"></a>Esempio di tipo di dati Dictionary e String

*[ProxyMode](./microsoft-edge-policies.md#proxymode):*

| Campo   | Valore                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Nome    | Microsoft Edge: ProxyMode                                                            |
| URI OMA | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| Tipo    | String                                                                               |
| Valore   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

## <a name="configure-microsoft-edge-in-intune-using-admx-ingestion"></a>Configurare Microsoft Edge in Intune tramite l'inserimento ADMX

Il modo consigliato per configurare Microsoft Edge con Microsoft Intune è quello di usare il profilo dei modelli amministrativi come descritto in [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune](./configure-edge-with-intune.md). Se desideri valutare un criterio attualmente non disponibile nei modelli amministrativi di Microsoft Edge in Intune, puoi configurare Microsoft Edge tramite le [impostazioni personalizzate per i dispositivi Windows 10 in Intune](/intune/configuration/custom-settings-windows-10).

Questa sezione descrive come:

1. [Inserire il file ADMX di Microsoft Edge in Intune](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [Impostare un criterio tramite l'URI OMA personalizzato in Intune](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> Come procedura consigliata, non usare un profilo URI OMA personalizzato né un profilo di modelli di amministrazione per configurare la stessa impostazione Microsoft Edge in Intune. Se distribuisci gli stessi criteri usando un URI OMA personalizzato e un profilo del modello amministrativo, ma con valori diversi, gli utenti otterranno risultati imprevedibili. Ti consigliamo di rimuovere il profilo URI OMA prima di usare un profilo di modelli di amministrazione.

### <a name="ingest-the-microsoft-edge-admx-file-into-intune"></a>Inserire il file ADMX di Microsoft Edge in Intune

In questa sezione viene descritto come inserire il modello amministrativo di Microsoft Edge (file **msedge.admx**) in Intune.

> [!WARNING]
> Non modificare il file ADMX prima di inserirlo.

Per inserire il file ADMX, segui questi passaggi:

1. Scarica il file dei modelli dei criteri di Microsoft Edge (MicrosoftEdgePolicyTemplates.cab) nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise) ed estrai il contenuto. Il file da inserire è **msedge. admx**.
2. Accedi al [portale di Microsoft Azure](https://portal.azure.com).
3. Seleziona **Intune** in _Tutti i servizi_ oppure cerca Intune nella casella di ricerca del portale.
4. Nel pannello _Microsoft Intune - Panoramica_ seleziona **Configurazione del dispositivo** | **Profili**.
5. Sulla barra dei comandi superiore seleziona **+ Crea profilo**.

   ![Creare un profilo del dispositivo](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. Specifica le informazioni sul profilo seguenti:

   - **Nome**: immetti un nome descrittivo Per questo esempio immetti "Configurazione inserita ADMX Microsoft Edge".
   - **Descrizione**: immetti una descrizione facoltativa per il profilo.
   - **Piattaforma**: seleziona "Windows 10 e versioni successive"
   - **Tipo di profilo**: seleziona "Personalizzato"

7. In **Impostazioni OMA-URI personalizzate** fai clic su **Aggiungi** per aggiungere un inserimento ADMX.

   ![Aggiungere un inserimento per URI OMA](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. In **Aggiungi riga** specifica le informazioni seguenti:

   - **Nome**: immetti un nome descrittivo Per questo esempio usai "Inserimento ADMX Microsoft Edge".
   - **Descrizione**: immetti una descrizione facoltativa per l'impostazione.
   - **OMA-URI**: immetti "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"
   - **Tipo di dati**: seleziona "String"
   - **Valore**: questa area di input viene visualizzata dopo che hai selezionato **Tipo di dati**. Aprire il file msedge.admx dal file dei modelli di criteri di Microsoft Edge estratto nel passaggio 1. Copia **TUTTO il testo** dal file msedge.admx e incollalo nell'area di testo **Valore** mostrata nella schermata seguente.

        ![Aggiungere un inserimento ADMX](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - Fai clic su **OK**.

9. In **Impostazioni OMA-URI personalizzate** fai clic su **OK**.
10. In **Crea profilo** fai clic su **Crea**. Nella schermata successiva vengono visualizzate le informazioni sul profilo creato.

    ![Informazioni sul nuovo profilo del dispositivo ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <a name="set-a-policy-using-custom-oma-uri-in-intune"></a>Impostare un criterio tramite l'URI OMA personalizzato in Intune

> [!NOTE]
> Prima di usare i passaggi illustrati in questa sezione, devi completare i passaggi descritti in [Inserire il file ADMX di Microsoft Edge in Intune](#ingest-the-microsoft-edge-admx-file-into-intune).

1. Accedi al [portale di Microsoft Azure](https://portal.azure.com).
2. Seleziona **Intune** in _Tutti i servizi_ oppure cerca Intune nella casella di ricerca del portale.
3. Vai a **Intune**>**Configurazione del dispositivo**>**Profili**.
4. Seleziona il profilo "Configurazione inserita ADMX Microsoft Edge" o il nome usato per il profilo.
5. Per aggiungere le impostazioni dei criteri di Microsoft Edge, devi aprire **Impostazioni OMA-URI personalizzate**. In **Gestisci**, fai clic su **Proprietà**, quindi su **Impostazioni**.

    ![Configurare le impostazioni del profilo](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. In **Impostazioni OMA-URI personalizzate** fai clic su **Aggiungi**.

    ![Aggiungere una riga alle impostazioni URI OMA](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. In **Aggiungi riga** specifica le informazioni seguenti:

   - **Nome**: immetti un nome descrittivo Si consiglia di usare il nome del criterio da configurare. Per questo esempio, usa "ShowHomeButton".
   - **Descrizione**: (facoltativo) immetti una descrizione per l'impostazione.
   - **OMA-URI**: immetti il valore URI OMA per il criterio. Usando il criterio "ShowHomeButton" come esempio, usa questa stringa: "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"
   - **Tipo di dati**: seleziona il tipo di dati delle impostazioni del criterio. Per il criterio "ShowHomeButton", usa "String"
   - **Valore**: immetti l'impostazione che si desidera configurare per il criterio. Per "ShowHomeButton", ad esempio, immettere “\<enabled/>”. Nella schermata seguente vengono visualizzate le impostazioni per configurare un criterio.

        ![Aggiungere una riga, impostazioni OMA-URI personalizzate](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - Fai clic su **OK**.

8. In **Impostazioni OMA-URI personalizzate** fai clic su **OK**.
9. Nel profilo "**Configurazione inserita ADMX Microsoft Edge - Proprietà**" (o nel nome usato), fai clic su **Salva**.

Dopo aver creato il profilo e impostato le proprietà, devi [assegnare il profilo in Microsoft Intune](/intune/configuration/device-profile-assign).

#### <a name="confirm-that-the-policy-was-set"></a>Verificare che il criterio sia stato impostato

Usa la procedura seguente per verificare che i criteri di Microsoft Edge usino il profilo creato. Concedi a Microsoft Intune tempo per propagare il criterio a un dispositivo assegnato nell'esempio di profilo "Configurazione inserita Microsoft Edge ADMX".

1. Apri Microsoft Edge e vai a *edge://policy*.
2. Nella pagina **Criteri** verifica se il criterio impostato nel profilo è elencato.
3. Se il criterio non viene visualizzato, vedi [Diagnosticare gli errori di MDM in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) oppure [Risoluzione dei problemi relativi alle impostazioni dei criteri](#troubleshoot-a-policy-setting).

#### <a name="troubleshoot-a-policy-setting"></a>Risoluzione dei problemi relativi alle impostazioni dei criteri

Se un criterio di Microsoft Edge non ha effetto, prova a eseguire queste le operazioni:

Apri la pagina *edge://policy* nel dispositivo di destinazione (un dispositivo a cui hai assegnato il profilo in Microsoft Intune) e cerca il criterio. Se il criterio non è presente nella pagina *edge://policy*, prova le operazioni seguenti:

- Verificare che il criterio sia nel Registro di sistema e che sia corretto. Nel dispositivo di destinazione apri l'editor del Registro di sistema di Windows 10 (**tasto Windows + r**, immetti "*regedit*" e quindi premi **Invio**.) Verifica che il criterio sia definito in modo corretto nel percorso *\Software\Policies\ Microsoft\Edge*. Se non trovi il criterio nel percorso previsto, il criterio non è stato inserito correttamente nel dispositivo.
- Verifica che il percorso URI OMA sia corretto e che il valore sia una stringa XML valida. Se uno di questi elementi non è corretto, il criterio non viene inserito nel dispositivo di destinazione.

Per altri suggerimenti per la risoluzione dei problemi, vedi [Configurare Microsoft Intune](/intune/fundamentals/setup-steps) e [Sincronizzare dispositivi](/intune/remote-actions/device-sync).

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.](configure-edge-with-intune.md)
- [Gestione di dispositivi mobili](/windows/client-management/mdm/)
- [Usare le impostazioni personalizzate per i dispositivi Windows 10 in Intune](/intune/configuration/custom-settings-windows-10)
- [Configurazione dei criteri delle app Win32 e Desktop Bridge](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [Informazioni sui criteri con backup ADMX](/windows/client-management/mdm/understanding-admx-backed-policies)