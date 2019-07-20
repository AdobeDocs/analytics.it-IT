---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all'altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all'altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
seo-title: Variabili dinamiche
solution: Analytics
subtopic: Variabili
title: Variabili dinamiche
topic: Sviluppatore e implementazione
uuid: 1 c 6 db 083-570 e -4 bc 4-858 d -84 cf 46 e 7 bec 8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Variabili dinamiche

Le variabili dinamiche consentono di copiare i valori da una variabile all'altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.

Le variabili dinamiche vengono utilizzate quando si acquisiscono gli stessi dati (ad esempio, codici di tracciamento campagna) in più variabili contemporaneamente. Questa è una prassi comune nei casi in cui i rapporti diversi offrono metriche uniche e importanti. For example, capturing internal search keywords in a [!UICONTROL Custom Conversion] variable and in a [!UICONTROL Custom Traffic] variable lets you view the [!UICONTROL Revenue] and the [!UICONTROL Weekly Unique Visitors] metrics associated with these keywords, respectively.

Le variabili dinamiche sono utili anche per visualizzare i dati in varie condizioni di reporting. Un codice di tracciamento campagna può essere acquisito in più evar con diverse impostazioni di scadenza e di scadenza cookie. Questo consente agli utenti di scegliere il modo in cui attribuire le metriche di conversione a queste campagne.

>[!NOTE]
>
>Le variabili dinamiche non sono supportate in combinazione con cookie (s_ cc, s_ sq, s_ fid, s_ vi e cookie impostati da un plug-in). `D=<cookie value>`Non è possibile utilizzare.

Un vantaggio significativo delle variabili dinamiche è la capacità di acquisire stringhe lunghe di dati in più variabili, senza passare più volte la stringa lunga. Alcuni browser limitano la lunghezza massima delle richieste HTTP GET (inclusa la richiesta di immagine Adobe). L'utilizzo delle variabili dinamiche garantisce che tutti i dati vengano acquisiti riducendo la lunghezza della richiesta ai server Adobe nei casi in cui i dati vengono duplicati su più variabili.

In the Adobe image request that occurs on the page view, if you are using dynamic variables to copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1], you would see `v1=D=c1`. If eVar1 received a value previously in the request, Adobe's servers dynamically copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1] during data processing. As a result, the value originally passed using [!UICONTROL Custom Traffic 1] also appears in the [!UICONTROL Custom Conversion 1] reports.

Dynamic variables are passed by setting a variable to the desired value and then setting other variables to `D=[variable abbreviation]`. For abbreviations for each variable, see [Data Collection Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md). Le variabili dinamiche possono estrarre dati dalle posizioni seguenti:

* Altre variabili di stringa query
* Intestazioni HTTP (fatta eccezione per l'intestazione HTTP cookie)

Per creare una variabile dinamica, aggiungi un prefisso speciale all'inizio del valore. Il prefisso predefinito è "D =". Esistono due metodi per segnalazione di variabili dinamiche:

* Utilizzate un prefisso predefinito D = (ad esempio: s. prop 1 = "D = User-Agent")
* Per le implementazioni non javascript, potete definire un prefisso personalizzato utilizzando il parametro di stringa query «D». For example, if the query-string parameter is `"&D=$"`, you can create a dynamic variable with the following command: `s.prop1="$User-Agent"` .

L'abbreviazione variabile utilizzata deve corrispondere al nome del parametro variabile trasmesso nella richiesta di immagine. Alcune variabili presentano più parametri accettati in casi diversi. For example, `pageName=` and `gn=` both pass the page name, but the latter is most often used in mobile and hard-coded implementations. If the image request uses `pageName=` to pass the page name, then `D=pageName` is acceptable but `D=gn` is not. If the image request uses `gn=`, then `D=gn` is acceptable, but `D=pageName` is not.

Le informazioni seguenti si applicano alle variabili dinamiche:

* Le variabili dinamiche funzionano con tutte le versioni del codice appmeasurement.
* Le variabili dinamiche sono con distinzione tra maiuscole e minuscole.
* Le variabili dinamiche supportano stringhe letterali contenute tra virgolette.
* La sostituzione variabile dinamica si verifica prima delle regole di elaborazione, VISTA e di altro tipo.
* Il prefisso variabile dinamico "D =" deve trovarsi all'inizio del valore della variabile non in mezzo. For example, use `c2='D="test7"+User-Agent'` rather than `c2='"test7"+D=User-Agent'` .

* Come per tutte le tecniche di implementazione, Adobe consiglia vivamente di testare le implementazioni dinamiche delle variabili in un ambiente di sviluppo prima di distribuire alla produzione. Poiché le stringhe complete copiate non sono visibili negli strumenti di debug lato client, controlla i report di Analytics interessati per confermare l'implementazione corretta.
* Durante la copia di valori tra variabili con lunghezze massime diverse, notare che la copia di un valore che superi la lunghezza massima della variabile di destinazione causa il troncamento. For example, [!UICONTROL Custom Traffic] variables have 100-character limits and [!UICONTROL Custom Conversion] variables have 255-characters limits. When copying a 150-character value from s.eVar1 to s.prop1 using dynamic variables, this value is truncated in the [!UICONTROL Custom Traffic] report at 100 characters.

## Dynamic Variable Examples {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Esempi di variabili dinamiche utilizzabili in Analytics.

In the Adobe image request that occurs on the page view, if you are using dynamic variables to copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1], you would see `v1=D=c1`. If eVar1 received a value previously in the request, Adobe's servers dynamically copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1] during data processing. As a result, the value originally passed using [!UICONTROL Custom Traffic 1] also appears in the [!UICONTROL Custom Conversion 1] reports.

Note that the `D=[variable]` value should be in quotes. Il codice Analytics considera questa stringa come una stringa. La stringa verrà codificata in URL quando viene trasmessa in Analytics (come vedrete se visualizzate la richiesta in digitalpulse Debugger o in un'utility simile). Questo è normale. Adobe's servers recognize the `D=[variable]` construction and will copy the appropriate value when they encounter this string.

>[!NOTE]
>
>Quando si utilizza la richiesta di immagine per tenere traccia dei collegamenti, il tipo di collegamento (download = lnk_ d, exit = lnk_ e o custom link = lnk_ o) deve essere definito, così come l'URL/nome collegamento (pev 2). Links require manual implementation by inserting code within the `<a href>` tag.

>[!NOTE]
>
>Le variabili dinamiche non sono supportate in combinazione con cookie (s_ cc, s_ sq, s_ fid, s_ vi e cookie impostati da un plug-in). `D=<cookie value>`Non è possibile utilizzare.

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Esempio javascript </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. evar 1 = "D = pagename" </code>
  </td> 
   <td colname="col2"> <p>Acquisisce il valore pagename in evar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 ='D = v 2 + ": " + c 2 '&amp; amp; nbsp; </code>
  </td> 
   <td colname="col2"> <p>Concatena evar 2: prop 2 in prop 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 = s. evar 1 = "D = g" &amp; amp; nbsp; </code>
  </td> 
   <td colname="col2"> <p>Trasmette l'URL della pagina sia a prop 1 che evar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. evar 1 = "D = v 0" </code>
  </td> 
   <td colname="col2"> <p>Acquisisce la campagna in evar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 ='D = User-Agent + "; - " + Accept-Language" </code>
  </td> 
   <td colname="col2"> <p>Concatena l'agente utente e accetta le intestazioni del linguaggio in prop 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>s. prop 1 = "D = User-Agent" </code>
  </td> 
   <td colname="col2"> <p>Acquisisce l'agente utente in prop 1, </p> </td> 
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
    <code class="syntax javascript">/b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 1 = ~ ~ v 0 /b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 1 = ~ ~ campaign /b/ss/rsid/? gn = Home &amp; c 1 = D % 3 dv 0% 3 d is /b/ss/rsid/? gn = Home &amp; c 1 = % 5 b % 5 bv 0% 5 d % 5 d % 5 b </code>
  </td> 
   <td colname="col2"> <p>Quattro modi per impostare prop 1 su una campagna </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>/b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 2 = ~ ~ x-up-subno </code>
  </td> 
   <td colname="col2"> <p> Estrae l'intestazione x-up-subno in prop 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>c 1 = D % 3 duser-Agent </code>
  </td> 
   <td colname="col2"> <p> Imposta prop 1 su una variabile dinamica riempita con l'intestazione HTTP dell'agente utente </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c 1 = D % 3 D % 22 test % 22 </code>
  </td> 
   <td colname="col2"> <p> Imposta prop 1 su variabile dinamica riempita con la stringa "test". Questo diventa più utile se utilizzato con la concatenazione che utilizza l'operatore +. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c 1 = D % 3 D % 22 US % 3 A % 20% 22% 2 buser-Agent </code>
  </td> 
   <td colname="col2"> <p> Rende prop 1 una variabile dinamica riempita con l'agente utente prefissato da "UA: " " </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; vid = D % 3 DX-TM-ANTID </code>
  </td> 
   <td colname="col2"> <p> Questo esempio cerca un'intestazione univoca, che in questo caso è X-TM-ANTID. </p> </td> 
  </tr> 
 </tbody> 
</table>
