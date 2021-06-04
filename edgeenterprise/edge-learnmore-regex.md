---
title: Sintassi delle espressioni regolari 2
ms.author: comanea
author: dan-wesley
manager: seanlyn
ms.date: 06/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sintassi delle espressioni regolari 2
ms.openlocfilehash: 9654a25d2c0474601fb719b145ebb1f59241a6d9
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980208"
---
# Sintassi delle espressioni regolari 2 (RE2.h)

Le espressioni regolari sono una notazione per la descrizione dei set di stringhe di caratteri. Quando una stringa si trova nel set descritto da una espressione regolare, spesso diciamo che l'espressione regolare corrisponda alla stringa.

L'espressione regolare più semplice è un carattere letterale singolo. Fatta eccezione per i metacaratteri, come *\*+?()|*, i caratteri corrispondono a se stessi. Per trovare la corrispondenza di un metacarattere, usare la barra rovesciata come carattere di escape: \+ corrisponde a un carattere “più” alfabetico.

Due espressioni regolari possono essere alterate o concatenate per formare una nuova espressione regolare: se *e<sub>1</sub>* corrisponde a _s_ ed *e<sub>2</sub>* corrisponde a _t_, allora *e<sub>1</sub>* | *e<sub>2</sub>* corrisponde a _s_ o a _t_, ed *e<sub>1</sub>* *e<sub>2</sub>*  corrisponde a _st_.

I metacaratteri _\*_ , _+_ , e _?_ sono operatori di ripetizione: *e<sub>1</sub>* _\*_ corrisponde a una sequenza di zero o più stringe (possibilmente differenti), ciascuna delle quali corrisponde ad *e<sub>1</sub>*; *e<sub>1</sub>* _+_ corrisponde a una o più; *e<sub>1</sub>* _?_ corrisponde a zero o una.

La precedenza degli operatori, dal legame più debole al più forte, è il seguente: alternanza, concatenazione, e infine ripetizione. Le parentesi esplicite possono essere usate per trasmettere significati differenti, come nelle espressioni aritmetiche. Alcuni esempi: _ab|cd_ equivale ad _(ab)|(cd)_ ; _ab\*_ è equivalente ad _a(b\*)_ .

La sintassi descritta finora è in gran parte presa dalla tradizionale sintassi delle espressioni regolari _egrep_ di Unix. Questo sottogruppo è sufficiente per descrivere tutti i linguaggio regolari: in parole povere, un linguaggio regolare è un set di stringhe che possono essere verificate in un testo con un solo passaggio, usando solo una quantità finita di memoria. Linguaggi più recenti per le espressione regolari (come Perl e quelli che l'hanno copiato) hanno aggiunto numerosi nuovi operatori e sequenze di escape, che rendono le espressioni regolari più concise e a volte più criptiche, ma di norma non più potenti.

Questa pagina elenca la sintassi delle espressioni regolari accettate da RE2.

Elenca anche alcune sintassi accettate da PCRE, PERL e VIM.

##  <a name="syntax-tables"></a>Tabelle della sintassi

| Tipi di espressioni a caratteri singoli | Esempi |
| --- | --- |
| qualsiasi carattere, eventualmente includendo newline (s=true) | . |
| classe di caratteri | [xyz] |
| classe di carattere negativa | [^xyz] |
| classe di caratteri di Perl ([collegamento](#user-content-perl)) | \d |
| classe di carattere di Perl negati | \D |
| classe di caratteri ASCII ([collegamento](#user-content-ascii)) | [[:alpha:]] |
| classe di carattere ASCII negati | [[:^alpha:]] |
| classe di caratteri Unicode (nome di una lettera) | \pN |
| classe di carattere Unicode negati  | \p{Greek} |
| classe di caratteri Unicode negati (nome di una lettera) | \PN |
| classe di caratteri Unicode negati  | \P{Greek} |

| | Costrutti |
| --- | --- |
| xy | x seguito da y |
| x\|y | x o y (x preferibile) |

| | Ripetizioni |
| --- | --- |
| x\* | zero o più x, più è preferibile |
| x+ | una o più x, più è preferibile |
| x? | zero o una x, una è preferibile |
| x{n,m} | n o n+1 o ... o m x, più è preferibile |
| x{n,} | n o più x, più è preferibile |
| x{n} | esattamente n x |
| x\*? | zero o più x, meno è preferibile |
| x+? | una o più x, meno è preferibile |
| x?? | zero o una x, zero è preferibile |
| x{n,m}? | n o n+1 o ... o m x, meno è preferibile |
| x{n,}? | n o più x, meno è preferibile |
| x{n}? | esattamente n x |
| x{} | (≡ x\*) (NON SUPPORTATO) VIM |
| x{-} | (≡ x\*?) (NON SUPPORTATO) VIM |
| x{-n} | (≡ x{n}?) (NON SUPPORTATO) VIM |
| x= | (≡ x?) (NON SUPPORTATO) VIM |

Limitazione dell'implementazione: le forme di conteggio x{n,m}, x{n,} e x{n} rifiutano le forme che creano un conteggio minimo o massimo di ripetizioni superiore a 1000. Le ripetizioni illimitate non sono soggete a questa limitazione.

| | Ripetizioni possessive |
| --- | --- |
| x\*+ | zero o più x, possessiva (NON SUPPORTATO) |
| x++ | una o più x, possessiva (NON SUPPORTATO) |
| x?+ | zero o una x, possessiva (NON SUPPORTATO) |
| x{n,m}+ | n or ... o m x, possessivo (NON SUPPORTATO) |
| x{n,}+ | n o più x, possessiva (NON SUPPORTATO) |
| x{n}+ | esattamente n x, possessiva (NON SUPPORTATO) |

| | Raggruppamento |
| --- | --- |
| (re) | gruppo di cattura numerato (sottocorrispondenza) |
| (?P&lt;nome&gt;re) | gruppo di cattura numerato nominato &amp; (sottocorrispondenza) |
| (?&lt;nome&gt;re) | gruppo di cattura numerato nominato &amp; (sottocorrispondenza) (NON SUPPORTATO) |
| (?&#39;nome&#39;re) | gruppo di cattura numerato nominato &amp; (sottocorrispondenza) (NON SUPPORTATO) |
| (?:re) | gruppo non di cattura |
| (?flags) | imposta contrassegni nel gruppo corrente; non catturante |
| (?flags:re) | imposta contrassegni durante re; non catturante |
| (?#text) | commento (NON SUPPORTATO) |
| (?\|x\|y\|z) | reimpostazione numerazione ramo (NON SUPPORTATO) |
| (?&gt;re) | corrispondenza possessiva di re (NON SUPPORTATO) |
| re@&gt; | corrispondenza possessiva di re (NON SUPPORTATO) VIM |
| %(re) | gruppo non di cattura (NON SUPPORTATO) VIM |

| | Flag |
| --- | --- |
| i | non sensibile alle maiuscole (false è predefinito) |
| m | modalità multiriga: ^ e $ corrispondono alla riga di inizio/fine oltre al testo di inizio/fine (false è predefinito) |
| s | lascia . corrispondenza \n (false è predefinito) |
| U | non greedy: scambia il significato di x\* e x\*?, x+ e x+?, ecc. (false è predefinito) |

La sintassi del contrassegno è xyz (configurazione) o -xyz (eliminazione) o xy-z (configura xy, elimina z).

|  | Stringhe vuote |
| --- | --- |
| ^ | all'inizio del testo o della riga (m=true) |
| $ | alla fine del testo (come \z non \Z) o della riga (m=true) |
| \A | all'inizio del testo |
| \b | al confine parola ASCII (\w su un lato e \W, \A, o \z sull'altro) |
| \B | non al confine parola ASCII |
| \g | all'inizio del sottotesto cercato (NON SUPPORTATO) PCRE |
| \G | alla fine dell'ultima corrispondenza (NON SUPPORTATO) PERL |
| \Z | alla fine del testo o prima di una nuova riga alla fine del testo (NON SUPPORTATO) |
| \z | alla fine del testo |
| (?=re) | prima del testo che corrisponde a re (NON SUPPORTATO) |
| (?!re) | prima del testo che non corrisponde a re (NON SUPPORTATO) |
| (?&lt;=re) | dopo il testo che corrisponde a re (NON SUPPORTATO) |
| (?&lt;!re) | dopo il testo che non corrisponde a re (NON SUPPORTATO) |
| re&amp; | prima del testo che corrisponde a re (NON SUPPORTATO) VIM |
| re@= | prima del testo che corrisponde a re (NON SUPPORTATO) VIM |
| re@! | prima del testo che non corrisponde a re (NON SUPPORTATO) VIM |
| re@&lt;= | dopo il testo che corrisponde a re (NON SUPPORTATO) VIM |
| re@&lt;! | dopo il testo che non corrisponde a re (NON SUPPORTATO) VIM |
| \zs | imposta inizio della corrispondenza (= \K) (NON SUPPORTATO) VIM |
| \ze | imposta fine della corrispondenza (= \K) (NON SUPPORTATO) VIM |
| \%^ | inizio del file (NON SUPPORTATO) VIM |
| \%$ | fine del file (NON SUPPORTATO) VIM |
| \%V | sullo schermo (NON SUPPORTATO) VIM |
| \%# | posizione cursore (NON SUPPORTATO) VIM |
| \%&#39;m | segna posizione m (NON SUPPORTATO) VIM |
| \%23l | nella riga 23 (NON SUPPORTATO) VIM |
| \%23c | nella colonna 23 (NON SUPPORTATO) VIM |
| \%23v | nella colonna virtuale 23 (NON SUPPORTATO) VIM |

|  | Sequenze di escape |
| --- | --- |
| \a | campanello (≡ \007) |
| \f | feed modulo (≡ \014) |
| \t | scheda orizzontale (≡ \011) |
| \n | nuova riga (≡ \012) |
| \r | ritorno a capo (≡ \015) |
| \v | carattere scheda verticale (≡ \013) |
| \* | letterale \*, per ogni segno di punteggiatura \* |
| \123 | codice di carattere ottale (fino a 3 cifre) |
| \x7F | codice carattere esadecimale (esattamente due cifre) |
| \x{10FFFF} | codice carattere esadecimale |
| \C | corrispondenza per un singolo byte anche nella modalità UTF-8 |
| \Q...\E | testo letterale ... anche se ... ha la punteggiatura |
| \1 | backreference (NON SUPPORTATO) |
| \b | cancelletto (NOT SUPPORTED) (usare \010) |
| \cK | carattere di controllo ^K (NON SUPPORTATO) (usare \001 ecc.) |
| \e | escape (NON SUPPORTATO) (usare \033) |
| \g1 | backreference (NON SUPPORTATO) |
| \g{1} | backreference (NON SUPPORTATO) |
| \g{+1} | backreference (NON SUPPORTATO) |
| \g{-1} | backreference (NON SUPPORTATO) |
| \g{name} | backreference nominato (NON SUPPORTATO) |
| \g&lt;nome&gt; | invoca sottoroutine (NON SUPPORTATO) |
| \g&#39;nome&#39; | invoca sottoroutine (NON SUPPORTATO) |
| \k&lt;nome&gt; | backreference nominato (NON SUPPORTATO) |
| \k&#39;nome&#39; | backreference nominato (NON SUPPORTATO) |
| \lX | X minuscola (NON SUPPORTATO) |
| \ux | X maiuscola (NON SUPPORTATO) |
| \L...\E | testo minuscolo ... (NON SUPPORTATO) |
| \K | reimposta inizio di $0 (NON SUPPORTATO) |
| \N{nome} | carattere Unicode nominato (NON SUPPORTATO) |
| \R | interruzione di riga (NON SUPPORTATO) |
| \U...\E | testo maiuscolo ... (NON SUPPORTATO) |
| \X | sequenza Unicode estesa (NON SUPPORTATO) |
| \%d123 | carattere decimale 123 (NON SUPPORTATO) VIM |
| \%xFF | carattere esadecimale FF (NON SUPPORTATO) VIM |
| \%o123 | carattere ottale 123 (NON SUPPORTATO) VIM |
| \%u1234 | carattere Unicode 0x1234 (NON SUPPORTATO) VIM |
| \%U12345678 | carattere Unicode 0x12345678 (NON SUPPORTATO) VIM |

|  | Elementi delle classi di caratteri |
| --- | --- |
| x | carattere singolo |
| A-Z | intervallo di caratteri (inclusivo) |
| \d | Classe di caratteri di Perl |
| [:foo:] | foo classe di caratteri ASCII |
| \p{Foo} | foo classe di caratteri Unicode |
| \pF | classe di caratteri Unicode F (nome di una lettera) |

|  | Classi di caratteri nominati come elementi di classi di caratteri |
| --- | --- |
| [\d] | cifre (≡ \d) |
| [^\d] | non cifre (≡ \D) |
| [\D] | non cifre (≡ \D) |
| [^\D] | non non cifre (≡ \d) |
| [[:nome:]] | classe ASCII nominati inclusa in una classe di caratteri (≡ [:nome:]) |
| [^[:nome:]] | classe ASCII nominata inclusa in una classe negata (≡ [:^nome:]) |
| [\p{Name}] | proprietà Unicode nominata inclusa in una classe di caratteri (≡ \p{Name}) |
| [^\p{Name}] | proprietà Unicode nominata inclusa in un carattere negato (≡ \P{Nome}) |

| <a name="user-content-perl"></a> | Classi di caratteri di Perl (tutti solo ASCII) |
| --- | --- |
| \d | cifre (≡ [0-9]) |
| \D | non cifre (≡ [^0-9]) |
| \s | spazio (≡ [\t\n\f\r]) |
| \S | non spazio (≡ [^\t\n\f\r]) |
| \w | caratteri di parola (≡ [0-9A-Za-z\_]) |
| \W | non caratteri di parola (≡ [^0-9A-Za-z\_]) |
| \h | spazio orizzontale (NON SUPPORTATO) |
| \H | non spazio orizzontale (NON SUPPORTATO) |
| \v | spazio verticale (NON SUPPORTATO) |
| \V | non spazio verticale (NON SUPPORTATO) |

|<a name="user-content-ascii"></a>  | Classe di caratteri di ASCII |
| --- | --- |
| [[:alnum:]] | alfanumerico (≡ [0-9A-Za-z]) |
| [[:alpha:]] | alfabetico (≡ [A-Za-z]) |
| [[:ascii:]] | ASCII (≡ [\x00-\x7F]) |
| [[:blank:]] | vuoto (≡ [\t]) |
| [[:cntrl:]] | controllo (≡ [\x00-\x1F\x7F]) |
| [[:digit:]] | cifre (≡ [0-9]) |
| [[:graph:]] | grafici (≡ `[!-~]` ≡ `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`) |
| [[:lower:]] | lettere minuscole (≡ [a-z]) |
| [[:print:]] | stampabili (≡ [-~] ≡ [[:graph:]]) |
| [[:punct:]] | punteggiatura (≡ [!-/:-@[-`{-~]) |
| [[:space:]] | spazio (≡ [\t\n\v\f\r]) |
| [[:upper:]] | lettere maiuscole (≡ [A-Z]) |
| [[:word:]] | caratteri di parola (≡ [0-9A-Za-z\_]) |
| [[:xdigit:]] | cifre esadecimali (≡ [0-9A-Fa-f]) |

| | Nomi di classi di caratteri di Unicode - categoria generale |
| --- | --- |
| C | altro |
| Cc | control |
| Cf | format |
| CN | punti di codice non assegnati (NON SUPPORTATO) |
| Co | uso privato |
| Cs | surrogato |
| L | lettera |
| LC | lettera con maiuscole/minuscole (NON SUPPORTATO) |
| L&amp; | lettera con maiuscole/minuscole (NON SUPPORTATO) |
| Ll | lettera minuscola |
| Lm | lettera modificatore |
| Lo | altra lettera |
| Lt | lettera del titolo |
| Lu | lettera maiuscola |
| M | segno |
| Mc | segno di spaziatura |
| Me | segno di chiusura |
| Mn | segno non di spaziatura |
| N | number |
| Nd | numero decimale |
| Nl | numero lettera |
| No | altro numero |
| P | punteggiatura |
| Pc | punteggiatura connettore |
| Pd | punteggiatura trattino |
| Pe | punteggiatura di chiusura |
| Pf | punteggiatura finale |
| Pi | punteggiatura iniziale |
| Po | altra punteggiatura |
| Ps | punteggiatura aperta |
| S | symbol |
| Sc | simbolo attuale |
| Sk | simbolo modificatore |
| Sm | simbolo matematico |
| So | altro simbolo |
| Z | separatore |
| Zl | separatore riga |
| Zp | separatore paragrafo |
| Zs | separatore spazio |

| Nomi di classi di caratteri di Unicode -- sistemi di scrittura |
| --- |
| Adlam |
| Ahom |
| Anatolico / geroglifici |
| Arabo |
| Armeno |
| Avestico |
| Balinese |
| Bamum |
| Bassa / Vah |
| Batak |
| Bengali |
| Bhaiksuki |
| Bopomofo |
| Brahmi |
| Braille |
| Buginese |
| Buhid |
| Canadese aborigeno |
| Cario |
| Caucasico / albanese |
| Chakma |
| Cham |
| Cherokee |
| Chorasmian |
| Comune |
| Copto |
| Cuneiforme |
| Cipriota |
| Cirillico |
| Deseret |
| Devanagari |
| Dives / Akuru |
| Dogra |
| Duployan |
| Egiziano / geroglifici |
| Elbasano |
| Elimaico |
| Etiopico |
| Georgiano |
| Glagolitico |
| Gotico |
| Grantha |
| Greco |
| Gujarati |
| Gunjala / Gondi |
| Gurmukhi |
| Han |
| Hangul |
| Hanifi / Rohingya |
| Hanunoo |
| Hatran |
| Ebraico |
| Hiragana |
| Imperiale / aramaico |
| Ereditato |
| Epigrafica / Pahlavi |
| Epigrafica / Partico |
| Giavanese |
| Kaithi |
| Kannada |
| Katakana |
| Kayah / Li |
| Kharoshthi |
| Khitan / segni piccoli |
| Khmer |
| Khojki |
| Khudawadi |
| Lao |
| Latino |
| Lepcha |
| Limbu |
| Lineare A |
| Lineare B |
| Lisu |
| Liciano |
| Lidio |
| Mahajani |
| Makasar |
| Malayalam |
| Mandaico |
| Manicheo |
| Marchen |
| Masaram / gondi |
| Medefaidrin |
| Meetei / mayek |
| Mende / kikakui |
| Meroitico / corsivo |
| Meroitico / geroglifici |
| Miao |
| Modi |
| Mongolo |
| Mro |
| Multani |
| Myanmar |
| Nabateo |
| Nandinagari |
| Nuovo / Tai / Lue |
| Newa |
| Nko |
| Nushu |
| Nyiakeng / Puachue / Hmong |
| Ogham |
| Ol / chiki |
| Antico / ungherese |
| Antico / italico |
| Antico / arabo settentrionale |
| Antico / permico |
| Antico / persiano |
| Antico / Sogdian |
| Antico / arabo meridionale |
| Antico / Turcico |
| Oriya |
| Osage |
| Osmanya |
| Pahawh / hmong |
| Palmireno |
| Pau / Cin / Hau |
| Phags / Pa |
| Fenicio |
| Psalter\_Pahlavi |
| Rejang |
| Runico |
| Samaritano |
| Saurashtra |
| Sharada |
| L'shaviano |
| Siddham |
| Linguaggio dei segni |
| Singalese |
| Sogdiano |
| Sora / sompeng |
| Soyombo |
| Sundanese |
| Syloti / nagri |
| Siriano |
| Tagalog |
| Tagbanwa |
| Tai / Le |
| Tai / Tham |
| Tai / Viet |
| Takri |
| Tamil |
| Tangut |
| Telugu |
| Thaana |
| Thai |
| Tibetano |
| Tifinagh |
| Tirhuta |
| Ugaritico |
| Vai |
| Wancho |
| Warang / Citi |
| Yezidi |
| Yi |
| Zanabazar / quadrato |

|  | Classi di caratteri di VIM |
| --- | --- |
| \i | carattere identificatore (NON SUPPORTATO) VIM |
| \I | \i tranne i numeri (NON SUPPORTATO) VIM |
| \k | carattere tastiera (NON SUPPORTATO) VIM |
| \K | \k tranne numeri (NON SUPPORTATO) VIM |
| \f | carattere nome di file (NON SUPPORTATO) VIM |
| \F | \f tranne numeri (NON SUPPORTATO) VIM |
| \p | caratteri stampabili (NON SUPPORTATO) VIM |
| \P | \p tranne caratteri (NON SUPPORTATO) VIM |
| \s | carattere spazio (≡ [\t]) (NON SUPPORTATO) VIM |
| \S | carattere non spazio (≡ [^ \t]) (NON SUPPORTATO) VIM |
| \d | cifre (≡ [0-9]) VIM |
| \D | non \d VIM |
| \x | cifre esadecimali (≡ [0-9A-Fa-f]) (NON SUPPORTATO) VIM |
| \X | non \x (NON SUPPORTATO) VIM |
| \o | cifre ottali (≡ [0-7]) (NON SUPPORTATO) VIM |
| \O | non \o (NON SUPPORTATO) VIM |
| \w | carattere di parola VIM |
| \W | non \w VIM |
| \h | inizio carattere di parola (NON SUPPORTATO) VIM |
| \H | non \h (NON SUPPORTATO) VIM |
| \a | alfabetico (NON SUPPORTATO) VIM |
| \A | non \a (NOT SUPPORTED) VIM |
| \l | minuscola (NON SUPPORTATO) VIM |
| \L | non minuscola (NON SUPPORTATO) VIM |
| \u | maiuscola (NON SUPPORTATO) VIM |
| \U | non maiuscola (NON SUPPORTATO) VIM |
| \_x | \x più newline, per qualsiasi x (NON SUPPORTATO) VIM |
| \c | ignora maiuscola/minuscola (NON SUPPORTATO) VIM |
| \C | corrispondenza maiuscola/minuscola (NON SUPPORTATO) VIM |
| \m | magic (NON SUPPORTATO) VIM |
| \M | no magic (NON SUPPORTATO) VIM |
| \v | very magic (NON SUPPORTATO) VIM |
| \V | very no magic (NON SUPPORTATO) VIM |
| \Z | ignora differenze nei caratteri di combinazione di Unicode (NON SUPPORTATO) VIM |

|  | Magic |
| --- | --- |
| (?{code}) | codice Perl arbitrario (NON SUPPORTATO) PERL |
| (??{code}) | codice Perl arbitrario posticipato (NON SUPPORTATO) PERL |
| (?n) | invocazione ricorsiva gruppo n di cattura regexp (NON SUPPORTATO) |
| (?+n) | invocazione ricorsiva per gruppo relativo +n (NON SUPPORTATO) |
| (?-n) | invocazione ricorsiva per gruppo relativo -n (NON SUPPORTATO) |
| (?C) | Invocazione PCRE (NON SUPPORTATO) CPRE |
| (?R) | invocazione ricorsiva intero regexp (≡ (?0)) (NON SUPPORTATO) |
| (?&amp;nome) | invocazionericorsiva per gruppo nominato (NON SUPPORTATO) |
| (?P=nome) | backreference nominato (NON SUPPORTATO) |
| (?P&gt;nome) | invocazione ricorsiva per gruppo nominato (NON SUPPORTATO) |
| (?(cond)true|false) | ramo condizionale (NON SUPPORTATO) |
| (?(cond)true) | ramo condizionale (NON SUPPORTATO) |
| (\*ACCEPT) | rende i regexps simili a Prolog (NON SUPPORTATO) |
| (\*COMMIT) | (NON SUPPORTATO) |
| (\*F) | (NON SUPPORTATO) |
| (\*FAIL) | (NON SUPPORTATO) |
| (\*MARK) | (NON SUPPORTATO) |
| (\*PRUNE) | (NON SUPPORTATO) |
| (\*SKIP) | (NON SUPPORTATO) |
| (\*THEN) | (NON SUPPORTATO) |
| (\*ANY) | imposta convenzione newline (NON SUPPORTATO) |
| (\*ANYCRLF) | (NON SUPPORTATO) |
| (\*CR) | (NON SUPPORTATO) |
| (\*CRLF) | (NON SUPPORTATO) |
| (\*LF) | (NON SUPPORTATO) |
| (\*BSR\_ANYCRLF) | imposta convenzione \R (NON SUPPORTATO) PCRE |
| (\*BSR\_UNICODE) | (NON SUPPORTATO) PCRE |

##  <a name="content-license"></a>Licenza dei contenuti

> [!NOTE]
> Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/). La pagina originale è disponibile [qui](https://github.com/google/re2/wiki/Syntax).
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.

##  <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)