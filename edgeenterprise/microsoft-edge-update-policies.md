---
title: Documentazione sui criteri di Microsoft Edge Update
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 10/07/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Documentazione per tutti i criteri supportati da Microsoft Edge Update
ms.openlocfilehash: feb7859f062ae39e2bbfe08d8e478386defb85cf
ms.sourcegitcommit: 4e6188ade942ca6fd599a4ce1c8e0d90d3d03399
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "11105570"
---
# Microsoft Edge - Criteri di aggiornamento
La versione più recente di Microsoft Edge include i seguenti criteri che puoi usare per controllare come e quando Microsoft Edge viene aggiornato.

Per informazioni su altri criteri disponibili in Microsoft Edge, vedi [Riferimento ai criteri del browser Microsoft Edge](microsoft-edge-policies.md)
> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.
## Criteri disponibili
In queste tabelle sono elencati tutti i criteri di gruppo correlati agli aggiornamenti disponibili in questa versione di Microsoft Edge. Usa i collegamenti nella tabella per ottenere altri dettagli su criteri specifici.

|||
|-|-|
|[Applicazioni](#applications)|[Preferenze](#preferences)|
|[Server proxy](#proxy-server)|[Microsoft Edge WebView](#microsoft-edge-webview)|

### [Applicazioni](#applications-policies)
|Nome criterio|Didascalia|
|-|-|
|[InstallDefault](#installdefault)|Consenti installazione predefinita|
|[UpdateDefault](#updatedefault)|Sostituzione dei criteri di aggiornamento predefinita|
|[Install](#install)|Consenti installazione (per canale)|
|[Update](#update)|Sostituzione dei criteri di aggiornamento (per canale)|
|[Allowsxs](#allowsxs)|Consenti esperienza browser Microsoft Edge affiancata|
|[CreateDesktopShortcutDefault](#createdesktopshortcutdefault)|Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita|
|[CreateDesktopShortcut](#createdesktopshortcut)|Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione (per canale)|
|[RollbackToTargetVersion](#rollbacktotargetversion)|Eseguire il ripristino dello stato precedente della versione di destinazione (per canale)|
|[TargetVersionPrefix](#targetversionprefix)|Sostituzione della versione di destinazione (in base al canale)|

### [Preferenze](#preferences-policies)
|Nome criterio|Didascalia|
|-|-|
|[AutoUpdateCheckPeriodMinutes](#autoupdatecheckperiodminutes)|Sostituzione del periodo di controllo dell'aggiornamento automatico|
|[UpdatesSuppressed](#updatessuppressed)|Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico|

### [Server proxy](#proxy-server-policies)
|Nome criterio|Didascalia|
|-|-|
|[ProxyMode](#proxymode)|Scegliere come specificare le impostazioni del server proxy|
|[ProxyPacUrl](#proxypacurl)|URL di un file PAC del proxy|
|[ProxyServer](#proxyserver)|Indirizzo o URL del server proxy|

### [Microsoft Edge WebView](#microsoft-edge-webview-policies)
|Nome criterio|Didascalia|
|-|-|
|[Installazione](#install-webview)|Consenti installazione|
|[Aggiornamenti](#update-webview)|Sostituzione dei criteri di aggiornamento|

## Criteri delle applicazioni

[Torna all'inizio](#microsoft-edge---update-policies)
### InstallDefault
#### Consenti installazione predefinita
>Microsoft Edge Update 1.2.145.5 e versioni successive

#### Descrizione
È possibile specificare il comportamento predefinito di tutti i canali per consentire o bloccare Microsoft Edge nei dispositivi collegati al dominio.

È possibile sostituire il criterio per i singoli canali abilitando il criterio "[Consenti installazione](#install)" per i canali specifici.

Disabilitando questo criterio, l'installazione di Microsoft Edge verrà bloccata. Questo riguarda solo l'installazione del software Microsoft Edge quando il criterio "[Consenti l'installazione](#install)" è impostato su Non configurato.

Questo criterio non impedisce l'esecuzione di Microsoft Edge Update, né impedisce l'installazione del software Microsoft Edge attraverso altri metodi.

Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: InstallDefault
- Nome Criteri di gruppo: Consenti installazione predefinita
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: InstallDefault
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### UpdateDefault
#### Sostituzione dei criteri di aggiornamento predefinita
>Microsoft Edge Update 1.2.145.5 e versioni successive

#### Descrizione
Consente di specificare il comportamento predefinito per tutti i canali in relazione al modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili per Microsoft Edge. Può essere sostituito per singoli canali specificando il criterio "[Sostituzione dei criteri di aggiornamento](#update)" per i canali specifici.

  Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:
   - Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.
   - Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.
   - Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale.
   - Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.

  Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile. Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.

  Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento](#update)".

  Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: UpdateDefault
- Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento predefinita
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: UpdateDefault
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000003
```
[Torna all'inizio](#microsoft-edge---update-policies)


### Install
#### Consenti installazione
>Microsoft Edge Update 1.2.145.5 e versioni successive

#### Descrizione
Specifica se è possibile installare un canale Microsoft Edge sui dispositivi collegati al dominio.

  Se abiliti questo criterio per un canale, Microsoft Edge non verrà bloccato dall'installazione.

  Se disabiliti questo criterio per un canale, Microsoft Edge verrà bloccato dall'installazione.

  Se non configuri questo criterio per un canale, il criterio "[Consenti installazione predefinita](#installdefault)" determina se gli utenti possono installare il canale di Microsoft Edge.

  Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: Install
- Nome Criteri di gruppo: Consenti installazione
- Percorso Criteri di gruppo: 
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: 
  - (Stabile): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### Update
#### Sostituzione dei criteri di aggiornamento
>Microsoft Edge Update 1.2.145.5 e versioni successive

#### Descrizione
Specifica il modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili da Microsoft Edge.

Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:
  - Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.
  - Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.
  - Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale. Non tutte le app forniscono un'interfaccia per questa opzione.
  - Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.

Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile. Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.

Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento predefinita](#updatedefault)".

Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406).

Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: Update
- Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento
- Percorso Criteri di gruppo: 
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome: 
  - (Stabile): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### Allowsxs
#### Consenti esperienza browser Microsoft Edge affiancata
>Microsoft Edge Update 1.2.145.5 e versioni successive

#### Descrizione
Questo criterio consente a un utente di eseguire Microsoft Edge (Edge HTML) e Microsoft Edge (basato su Chromium) in modalità affiancata.

Se questo criterio è impostato su "Non configurato", Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.  Si tratta dello stesso comportamento correlato all'impostazione "Disabilitato".

L'impostazione "Disabilitato" blocca un'esperienza affiancata e Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.  Si tratta dello stesso comportamento correlato all'impostazione "Non configurato".

Quando l'impostazione di questo criterio è "Abilitato", è possibile eseguire in modalità affiancata Microsoft Edge (basato su Chromium) e Microsoft Edge (Edge HTML) dopo l'installazione di Microsoft Edge (basato su Chromium).

Affinché questi criteri di gruppo abbiano effetto, è necessario configurarli prima dell'installazione automatica di Microsoft Edge (basato su Chromium) da Windows Update. Nota: un utente può bloccare l'aggiornamento automatico di Microsoft Edge (basato su Chromium) usando Blocker Toolkit di Microsoft Edge (basato su Chromium).
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: Allowsxs
- Nome Criteri di gruppo: Consenti esperienza browser Microsoft Edge affiancata
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: Allowsxs
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### CreateDesktopShortcutDefault
#### Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita
>Microsoft Edge Update 1.3.128.0 e versioni successive

#### Descrizione
Consente di specificare il comportamento predefinito per tutti i canali per la creazione di un collegamento sul desktop quando Microsoft Edge è installato.

  Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.
Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.
Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.
Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: CreateDesktopShortcutDefault
- Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: CreateDesktopShortcutDefault
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### CreateDesktopShortcut
#### Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione
>Microsoft Edge Update 1.3.128.0 e versioni successive

#### Descrizione
Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.
Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.
Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.
Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.

  Se questo criterio non viene configurato per un canale, la configurazione del criterio "[Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita](#createdesktopshortcutdefault)" determina la creazione del collegamento quando Microsoft Edge viene installato.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: CreateDesktopShortcut
- Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop dopo l'installazione
- Percorso Criteri di gruppo: 
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome: 
  - (Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### RollbackToTargetVersion
#### Esegui il ripristino dello stato precedente della versione di destinazione
>Microsoft Edge Update 1.3.133.3 e versioni successive

#### Descrizione
Specifica che Microsoft Edge Update dovrebbe eseguire il ripristino dello stato precedente delle installazioni di Microsoft Edge alla versione indicata in "[Sostituzione della versione di destinazione](#targetversionprefix)".

Questo criterio non ha alcun effetto, a meno che “[Sostituzione della versione di destinazione](#targetversionprefix)” sia impostato e “[Aggiorna criterio sostituzione](#update)” sia impostato su ATTIVO in uno dei seguenti stati (Consenti sempre gli aggiornamenti, Solo aggiornamenti automatici silenziosi, Solo aggiornamenti manuali).

Se disabiliti questo criterio o non lo configuri, le installazioni con una versione superiore a quella specificata da "[Sostituzione della versione di destinazione](#targetversionprefix)" verranno lasciate così come sono.

Se abiliti questi criteri, le installazioni che hanno una versione corrente superiore a quella specificata dall'override della”[Aggiorna criterio sostituzione](#targetversionprefix)" verranno declassate alla versione di destinazione.

È consigliabile installare l’ultima versione del browser Microsoft Edge per sfruttare la protezione degli aggiornamenti della sicurezza più recenti. Il ripristino di una versione precedente può comportare rischi di esposizione a problemi di sicurezza noti. Questo criterio deve essere usato come correzione temporanea per risolvere i problemi di aggiornamento del browser Microsoft Edge.

Prima di ripristinare temporaneamente la versione precedente del browser, è inoltre consigliabile abilitare la sincronizzazione ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) per tutti gli utenti dell'organizzazione. Se la sincronizzazione non viene abilitata, si rischia la perdita permanente dei dati di navigazione. Usa questo criterio a tuo rischio.

Nota: è possibile visualizzare tutte le versioni disponibili per il ripristino dello stato precedente qui [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).

Questo criteri viene applicato a Microsoft Edge versione 86 o successiva.

Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918).

Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: RollbackToTargetVersion
- Nome Criteri di gruppo: ripristina versione di destinazione
- Percorso Criteri di gruppo: 
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome: 
  - (Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### TargetVersionPrefix
#### Sostituzione della versione di destinazione
>Microsoft Edge Update 1.3.119.43 e versioni successive

#### Descrizione
Abilitando questo criterio e l'aggiornamento automatico, Microsoft Edge verrà aggiornato alla versione specificata da questo valore criterio.

Il valore del criterio deve essere una specifica versione di Microsoft Edge, ad esempio: 83.0.499.12.

Se sul dispositivo è installata una versione più recente di Microsoft Edge del valore specificato, Edge manterrà la versione più recente e non eseguirà il downgrade alla versione specificata.

In caso la versione specificata non esista o non sia formattata correttamente, Microsoft Edge manterrà la versione attuale e non verrà aggiornato automaticamente alle versioni future.

Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707).

Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: TargetVersionPrefix
- Nome Criteri di gruppo: Sostituzione della versione di destinazione
- Percorso Criteri di gruppo: 
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary
  - Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome: 
  - (Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Tipo valore: REG_SZ
##### Valore di esempio
```
83.0.499.12
```
[Torna all'inizio](#microsoft-edge---update-policies)


## Criteri delle preferenze

[Torna all'inizio](#microsoft-edge---update-policies)
### AutoUpdateCheckPeriodMinutes
#### Sostituzione del periodo di controllo dell'aggiornamento automatico
>Microsoft Edge Update 1.2.145.5 e versioni successive

#### Descrizione
Se abilitata, questo criterio consente di impostare un valore per il numero minimo di minuti che devono intercorrere tra i controlli dell'aggiornamento automatico. In caso contrario, per impostazione predefinita, l'aggiornamento automatico verifica la disponibilità degli aggiornamenti ogni 10 ore.

  Se desideri disabilitare tutti i controlli dell'aggiornamento automatico, imposta il valore su 0 (scelta non consigliata).
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: AutoUpdateCheckPeriodMinutes
- Nome Criteri di gruppo: Sostituzione del periodo di controllo dell'aggiornamento automatico
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: AutoUpdateCheckPeriodMinutes
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000578
```
[Torna all'inizio](#microsoft-edge---update-policies)


### UpdatesSuppressed
#### Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico
>Microsoft Edge Update 1.3.33.5 e versioni successive

#### Descrizione
Se abiliti questo criterio, i controlli degli aggiornamenti vengono soppressi ogni giorno a partire dall'ora e dal minuto specificati per un periodo stabilito (in minuti). La durata non è influenzata dall'ora legale. Ad esempio, se l'ora di inizio è 22.00 e la durata è 480 minuti, gli aggiornamenti verranno soppressi per esattamente 8 ore, indipendentemente dal fatto che l'ora legale venga avviata o termini durante questo periodo.

  Se disabiliti o non configuri questo criterio, i controlli degli aggiornamenti non vengono soppressi durante alcun periodo specifico.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: UpdatesSuppressed
- Nome Criteri di gruppo: Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico
  - Opzioni { Hour, Minute, Duration }
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome: 
  - UpdatesSuppressedDurationMin
  - UpdatesSuppressedStartHour
  - UpdatesSuppressedStartMin
- Tipo valore: REG_DWORD
##### Valore di esempio
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[Torna all'inizio](#microsoft-edge---update-policies)


## Criteri server proxy

[Torna all'inizio](#microsoft-edge---update-policies)
### ProxyMode
#### Scegliere come specificare le impostazioni del server proxy
>Microsoft Edge Update 1.3.21.81 e versioni successive

#### Descrizione
Consente di specificare le impostazioni del server proxy usate da Microsoft Edge Update.

  Se abiliti questo criterio, puoi scegliere una delle opzioni relative al server proxy seguenti:
   - Se scegli di non usare mai un server proxy e ti connetti sempre direttamente, tutte le altre opzioni vengono ignorate.
   - Se scegli di usare le impostazioni del proxy di sistema o di rilevare automaticamente il server proxy, tutte le altre opzioni vengono ignorate.
   - Se scegli la modalità proxy server fisso, puoi specificare altre opzioni nel criterio "[Indirizzo o URL del server proxy](#proxyserver)".
   - Se scegli di usare uno script proxy PAC, devi specificare l'URL per lo script nel criterio "[URL di un file PAC del proxy](#proxypacurl)".

  Se abiliti questo criterio, gli utenti dell'organizzazione non possono modificare le impostazioni proxy in Microsoft Edge Update.

  Se disabiliti o non configuri questo criterio, non vengono configurate impostazioni del server proxy, ma gli utenti dell'organizzazione possono scegliere le proprie impostazioni proxy per Microsoft Edge Update.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: ProxyMode
- Nome Criteri di gruppo: Scegliere come specificare le impostazioni del server proxy
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: ProxyMode
- Tipo valore: REG_SZ
##### Valore di esempio
```
fixed_servers
```
[Torna all'inizio](#microsoft-edge---update-policies)


### ProxyPacUrl
#### URL di un file PAC del proxy
>Microsoft Edge Update 1.3.21.81 e versioni successive

#### Descrizione
Consente di specificare un URL per un file di configurazione automatica del proxy (PAC).

  Se abiliti questo criterio, puoi specificare un URL per un file PAC per automatizzare il modo in cui Microsoft Edge Update seleziona il server proxy appropriato per il recupero di un particolare sito Web.

  Questo criterio viene applicato solo se sono state specificate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".

  Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: ProxyPacUrl
- Nome Criteri di Gruppo: URL di un file PAC del proxy
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: ProxyPacUrl
- Tipo valore: REG_SZ
##### Valore di esempio
```
https://www.microsoft.com
```
[Torna all'inizio](#microsoft-edge---update-policies)


### ProxyServer
#### Indirizzo o URL del server proxy
>Microsoft Edge Update 1.3.21.81 e versioni successive

#### Descrizione
Consente di specificare l'URL del server proxy per l'uso da parte di Microsoft Edge Update.

  Se abiliti questo criterio, puoi impostare l'URL del server proxy usato da Microsoft Edge Update nell'organizzazione.

  Questo criterio viene applicato solo se sono state selezionate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".

  Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: ProxyServer
- Nome Criteri di gruppo: Indirizzo o URL del server proxy
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome valore: ProxyServer
- Tipo valore: REG_SZ
##### Valore di esempio
```
https://www.microsoft.com
```
[Torna all'inizio](#microsoft-edge---update-policies)


## Criteri di Microsoft Edge WebView

[Torna all'inizio](#microsoft-edge---update-policies)
### Installa (WebView)
#### Consenti installazione
>Microsoft Edge Update 1.3.127.1 e versioni successive

#### Descrizione
Consente di specificare se è possibile installare Microsoft Edge WebView tramite Microsoft Edge Update.

  - Abilitando questo criterio, gli utenti possono installare Microsoft Edge WebView tramite Microsoft Edge Update.
  - Disabilitando questo criterio, gli utenti non possono installare Microsoft Edge WebView tramite Microsoft Edge Update.
  - Non configurando questo criterio, la configurazione del criterio "[Consenti installazione predefinita](#installdefault)" determina se gli utenti possono installare Microsoft Edge WebView tramite Microsoft Edge Update.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: Install
- Nome Criteri di gruppo: Consenti installazione
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Microsoft Edge WebView
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome: 
  - Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


### Aggiornameto (WebView)
#### Sostituzione dei criteri di aggiornamento
>Microsoft Edge Update 1.3.127.1 e versioni successive

#### Descrizione
Consente di specificare se abilitare gli aggiornamenti automatici per Microsoft Edge WebView. Microsoft Edge WebView è una componente usata dalle applicazioni per visualizzare il contenuto Web.
Gli aggiornamenti automatici sono abilitati per impostazione predefinita. Disabilitando gli aggiornamenti automatici per Microsoft Edge WebView potrebbero verificarsi problemi di compatibilità con le applicazioni che dipendono da questa componente.

  Abilitando questo criterio, Microsoft Edge Update gestisce gli aggiornamenti di Microsoft Edge WebView in base alla configurazione delle seguenti opzioni:
  - Consenti sempre gli aggiornamenti: gli aggiornamenti vengono scaricati e applicati automaticamente
  - Aggiornamenti disabilitati: gli aggiornamenti non vengono mai scaricati o applicati

  Non abilitando questo criterio, gli aggiornamenti verranno scaricati e applicati automaticamente.
#### Informazioni e impostazioni di Windows
##### Info su Criteri di gruppo (ADMX)
- Nome univoco Criteri di gruppo: Update
- Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento
- Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Microsoft Edge WebView
- Nome file ADMX Criteri di gruppo: msedgeupdate.admx
##### Impostazioni del Registro di sistema di Windows
- Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Nome: 
  - Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- Tipo valore: REG_DWORD
##### Valore di esempio
```
0x00000001
```
[Torna all'inizio](#microsoft-edge---update-policies)


## Vedere anche
  - [Configurazione di Microsoft Edge](configure-microsoft-edge.md)
  - [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)