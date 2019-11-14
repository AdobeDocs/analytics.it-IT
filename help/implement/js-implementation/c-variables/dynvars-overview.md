---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili dinamiche
topic: Developer and implementation
uuid: 1c6db083-570e-4bc4-858d-84cf46e7bec8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variabili dinamiche

Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.

Le variabili dinamiche vengono utilizzate quando si acquisiscono gli stessi dati (ad esempio, codici di tracciamento campagna) in più variabili contemporaneamente. Si tratta di una pratica comune nei casi in cui report diversi offrono metriche univoche e importanti. Ad esempio, l'acquisizione di parole chiave di ricerca interne in una [!UICONTROL Custom Conversion] variabile e in una [!UICONTROL Custom Traffic] variabile consente di visualizzare rispettivamente le [!UICONTROL Revenue] metriche e le [!UICONTROL Weekly Unique Visitors] metriche associate a tali parole chiave.

Le variabili dinamiche sono utili anche per visualizzare i dati in varie condizioni di reporting. Un codice di tracciamento campagna può essere acquisito in più eVar con diverse impostazioni di allocazione e scadenza cookie. Questo consente agli utenti di scegliere il modo in cui attribuire le metriche di conversione a queste campagne.

> [!NOTE] Le variabili dinamiche non sono supportate insieme ai cookie (s_cc, s_sq, s_fid, s_vi e qualsiasi cookie impostato da un plug-in). Non puoi usare `D=<cookie value>`.

Un vantaggio significativo delle variabili dinamiche è la capacità di acquisire lunghe stringhe di dati in più variabili senza passare la stringa lunga ripetutamente. Alcuni browser limitano la lunghezza massima delle richieste HTTP GET (inclusa la richiesta di immagini Adobe). L'utilizzo di variabili dinamiche garantisce che tutti i dati vengano acquisiti riducendo la lunghezza della richiesta ai server Adobe nei casi in cui i dati vengono duplicati su più variabili.

Nella richiesta di immagine Adobe che si verifica nella visualizzazione pagina, se utilizzate variabili dinamiche per copiare il valore di [!UICONTROL Custom Traffic 1] in [!UICONTROL Custom Conversion 1], vedrete `v1=D=c1`. Se eVar1 ha ricevuto un valore in precedenza nella richiesta, i server Adobe copiano in modo dinamico il valore di [!UICONTROL Custom Traffic 1] in [!UICONTROL Custom Conversion 1] durante l'elaborazione dei dati. Di conseguenza, nei [!UICONTROL Custom Traffic 1] rapporti appare [!UICONTROL Custom Conversion 1] anche il valore passato originariamente con l'aiuto.

Le variabili dinamiche vengono passate impostando una variabile sul valore desiderato e quindi impostando altre variabili su `D=[variable abbreviation]`. Per le abbreviazioni di ciascuna variabile, vedi Parametri [query raccolta](/help/implement/js-implementation/data-collection/query-parameters.md)dati. Le variabili dinamiche possono estrarre i dati dalle seguenti posizioni:

* Altre variabili query-stringa
* Intestazioni HTTP (tranne l’intestazione Cookie HTTP)

Per creare una variabile dinamica, aggiungete un prefisso speciale all’inizio del valore. Il prefisso predefinito è "D=". Esistono due metodi per contrassegnare le variabili dinamiche:

* Usate il prefisso predefinito D= (ad esempio: s.prop1="D=User-Agent" )
* Per le implementazioni non JavaScript, potete definire un prefisso personalizzato utilizzando il parametro della stringa di query "D". Ad esempio, se il parametro della stringa query è `"&D=$"`, è possibile creare una variabile dinamica con il seguente comando: `s.prop1="$User-Agent"` .

L’abbreviazione della variabile utilizzata deve corrispondere al nome del parametro della variabile passato nella richiesta di immagine. Alcune variabili presentano più parametri accettati utilizzati in casi diversi. Ad esempio, `pageName=` e `gn=` entrambi passano il nome della pagina, ma questi ultimi vengono utilizzati più spesso nelle implementazioni per dispositivi mobili e con codice rigido. Se la richiesta di immagine viene utilizzata `pageName=` per passare il nome della pagina, `D=pageName` è accettabile ma non lo `D=gn` è. Se la richiesta di immagine viene utilizzata `gn=`, `D=gn` è accettabile, ma non `D=pageName` lo è.

Le seguenti informazioni si applicano alle variabili dinamiche:

* Le variabili dinamiche funzionano con tutte le versioni del codice AppMeasurement.
* Le variabili dinamiche fanno distinzione tra maiuscole e minuscole.
* Le variabili dinamiche supportano stringhe letterali contenute tra virgolette.
* La sostituzione della variabile dinamica avviene prima delle regole di elaborazione, VISTA e altre elaborazioni.
* Il prefisso della variabile dinamica "D=" deve trovarsi all’inizio del valore della variabile non al centro. Ad esempio, utilizzate `c2='D="test7"+User-Agent'` anziché `c2='"test7"+D=User-Agent'` .

* Come per tutte le tecniche di implementazione, Adobe consiglia vivamente di sottoporre a test implementazioni di variabili dinamiche in un ambiente di sviluppo molto complesso prima di distribuirle in produzione. Poiché le stringhe complete copiate non sono visibili negli strumenti di debug sul lato client, controlla i report di Analytics interessati per confermare l'implementazione corretta.
* Durante la copia di valori tra variabili con lunghezze massime diverse, tenere presente che la copia di un valore superiore alla lunghezza massima della variabile di destinazione causa il troncamento. Ad esempio, [!UICONTROL Custom Traffic] le variabili hanno un limite di 100 caratteri e [!UICONTROL Custom Conversion] le variabili hanno un limite di 255 caratteri. Quando si copia un valore di 150 caratteri da s.eVar1 a s.prop1 utilizzando variabili dinamiche, questo valore viene troncato nel [!UICONTROL Custom Traffic] rapporto a 100 caratteri.

## Esempi di variabili dinamiche {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Esempi di variabili dinamiche utilizzabili in Analytics.

Nella richiesta di immagine Adobe che si verifica nella visualizzazione pagina, se utilizzate variabili dinamiche per copiare il valore di [!UICONTROL Custom Traffic 1] in [!UICONTROL Custom Conversion 1], vedrete `v1=D=c1`. Se eVar1 ha ricevuto un valore in precedenza nella richiesta, i server Adobe copiano in modo dinamico il valore di [!UICONTROL Custom Traffic 1] in [!UICONTROL Custom Conversion 1] durante l'elaborazione dei dati. Di conseguenza, nei [!UICONTROL Custom Traffic 1] rapporti appare [!UICONTROL Custom Conversion 1] anche il valore passato originariamente con l'aiuto.

Il `D=[variable]` valore deve essere racchiuso tra virgolette. Il codice Analytics lo gestisce come una stringa. La stringa verrà codificata tramite URL quando viene passata in Analytics (come vedrete se visualizzi la richiesta nel DigitalPulse Debugger o in un'utilità simile). Questo è normale. I server di Adobe riconoscono la `D=[variable]` costruzione e copiano il valore appropriato quando incontrano questa stringa.

> [!NOTE] Quando si utilizza la richiesta di immagine per tracciare i collegamenti, è necessario definire il tipo di collegamento (download=lnk_d, exit=lnk_e o collegamento personalizzato=lnk_o), così come l’URL/nome collegamento (pev2). I collegamenti richiedono l’implementazione manuale mediante l’inserimento di codice all’interno del `<a href>` tag .

> [!NOTE] Le variabili dinamiche non sono supportate insieme ai cookie (s_cc, s_sq, s_fid, s_vi e qualsiasi cookie impostato da un plug-in). Non puoi usare `D=<cookie value>`.

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Esempio JavaScript </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.eVar1="D=pageName" 
    </code> </td> 
   <td colname="col2"> <p>Acquisisce il valore pageName in eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=v2+":"+c2'&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>Concatenata eVar2:prop2 in prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1=s.eVar1="D=g"&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>Trasmette l’URL della pagina sia in prop1 che in eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.eVar1="D=v0" 
    </code> </td> 
   <td colname="col2"> <p>Cattura la campagna in eVar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=User-Agent+" ;- "+Accept-Language' 
    </code> </td> 
   <td colname="col2"> <p>Concatena l'agente utente e accetta le intestazioni della lingua in prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      s.prop1="D=User-Agent" 
    </code> </td> 
   <td colname="col2"> <p>Acquisisce l’agente utente in prop1, </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Esempio di richiesta immagine </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~v0 /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~campaign /b/ss/rsid/?gn=Home&amp;c1=D%3dv0%3d&nbsp;is /b/ss/rsid/?gn=Home&amp;c1=%5b%5bv0%5d%5d%5b
    </code> </td> 
   <td colname="col2"> <p>Quattro modi per impostare prop1 su una campagna </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c2=~~x-up-subno 
    </code> </td> 
   <td colname="col2"> <p> Inserisce l'intestazione x-su-subno in prop2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      c1=D%3DUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> Rende prop1 una variabile dinamica riempita con l'intestazione HTTP User-Agent </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22test%22 
    </code> </td> 
   <td colname="col2"> <p> Rende prop1 una variabile dinamica riempita con la stringa "test". Questo risulta più utile se utilizzato con la concatenazione che utilizza l'operatore +. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22US%3A%20%22%2BUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> Rende prop1 una variabile dinamica riempita con l'agente utente con il prefisso "UA:" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;vid=D%3DX-TM-ANTID 
    </code> </td> 
   <td colname="col2"> <p> Questo esempio cerca un'intestazione univoca, che in questo caso è X-TM-ANTID. </p> </td> 
  </tr> 
 </tbody> 
</table>
