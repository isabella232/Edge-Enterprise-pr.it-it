---
title: Interruzione dei download di file potenzialmente pericolosi
ms.author: kvice
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Interruzione dei download di file potenzialmente pericolosi
ms.openlocfilehash: 527b98b54cf03f6c116624296c63803b57a7f0c4
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642672"
---
# <a name="interrupting-downloads-of-potentially-dangerous-files"></a>Interruzione dei download di file potenzialmente pericolosi

Il componente per i criteri sul tipo di file di Microsoft Edge consente di classificare i file in base al livello di pericolosità, in modo che i file innocui (ad esempio i file `.txt`) possano essere scaricati liberamente, mentre i file potenzialmente pericolosi (ad esempio i file `.dll`) siano sottoposti a maggiori verifiche e a un'esperienza utente più consapevole in termini di sicurezza.

## <a name="determining-the-danger-level-of-a-file-type"></a>Determinazione del livello di pericolo di un tipo di file

Microsoft Edge eredita i criteri del tipo di file dal browser Chromium. È possibile visualizzare il contenuto corrente dell'elenco [qui](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb). Nell'elenco si vede che ogni tipo è associato a un livello di pericolo (danger_level), che può avere uno dei tre valori seguenti: `DANGEROUS` `NOT_DANGEROUS` o `ALLOW_ON_USER_GESTURE`.

I primi due sono semplici: **NOT_DANGEROUS** significa che il file è sicuro, anche se il download è stato accidentale. **DANGEROUS** significa che il browser deve sempre avvisare l'utente che il download potrebbe danneggiare il dispositivo.

La terza impostazione **ALLOW_ON_USER_GESTURE** è più sottile. Questi file sono potenzialmente pericolosi, ma molto probabilmente innocui se è stato l'utente ad avviare il download. Microsoft Edge consentirà a tali download di procedere automaticamente se vengono soddisfatte due condizioni:

1. La richiesta di rete che ha avviato il download è associata a un [gesto dell'utente](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/), ad esempio, l'utente ha fatto clic su un collegamento al download.
2. È stata registrata una visita all'origine di riferimento (la pagina che collega al download) precedente all'ultima mezzanotte (ad esempio, ieri o prima). Questo implica che l'utente ha già visitato il sito.

Il download procederà automaticamente anche se l'utente lo ha avviato in modo esplicito mediante il comando del menu di scelta rapida **Salva collegamento con nome**, se ha immesso l'URL del download direttamente nella barra degli indirizzi del browser o se Microsoft Defender SmartScreen ha indicato che il file è sicuro.

**Aggiornamento:** a partire dalla versione 91, Microsoft Edge interromperà i download in assenza del gesto richiesto.

## <a name="user-experience-for-downloads-lacking-gestures"></a>Esperienza utente per i download senza gesti

Se il download per un tipo potenzialmente pericoloso inizia senza il gesto dell'utente richiesto, Microsoft Edge indica che il download "è stato bloccato". Nel menu ... dell'elemento di download sono disponibili i comandi `Keep` e `Delete` per consentire all'utente di continuare o annullare il download.

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="Download bloccato":::

Nella pagina `edge://downloads` l'utente vedrà le stesse opzioni:

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="Messaggio con opzioni per continuare o eliminare":::

## <a name="enterprise-controls"></a>Controlli per le aziende

Anche se è improbabile che gli utenti riscontrino interruzioni dei download nei siti che usano ogni giorno, potrebbero riscontrarne per download legittimi in siti che usano raramente. Per semplificare l'esperienza utente in ambito aziendale, è disponibile un criterio di gruppo.

Le aziende possono usare [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) per specificare i tipi di file che possono essere scaricati da siti specifici senza interruzioni. Ad esempio, il criterio seguente consente di scaricare senza interruzioni file XML da contoso.com e woodgrovebank.com e di scaricare file MSG da qualsiasi sito.

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a>Tipi di file che richiedono un gesto

Gli ultimi [criteri per i tipi di file](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) sono stati pubblicati nel codice sorgente di Chromium. A maggio 2021, i tipi di file con un `danger_level` uguale a `ALLOW_ON_USER_GESTURE` su almeno una piattaforma del sistema operativo includono:
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="danger-level-may-vary-by-operating-system"></a>Il livello di pericolo può variare in base al sistema operativo

Le impostazioni del tipo di file a volte variano a seconda della piattaforma del sistema operativo client. Ad esempio, un file `.exe` non è pericoloso in Mac, mentre un `.applescript` è innocuo in Windows.
