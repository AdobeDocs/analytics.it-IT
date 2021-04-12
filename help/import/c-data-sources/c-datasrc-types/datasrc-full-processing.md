---
description: Origini dati supporta le variabili seguenti durante l'elaborazione dei dati come chiamata server standard (Generic (Generico) > Full Processing (Elaborazione completa)).
title: Elaborazione completa
topic: Sviluppatore e implementazione
exl-id: 9eb8c754-f4de-4483-934e-3f79134516ca
translation-type: tm+mt
source-git-commit: 4e8a79648b0573e68d9059c518f6ec8fb3d9a694
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 80%

---

# Elaborazione completa

>[!IMPORTANT]
>
>Adobe consiglia ai clienti di utilizzare l’ [API di inserimento dati in blocco (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) invece delle origini dati a elaborazione completa. Adobe prevede di rendere obsolete le origini dati per l’elaborazione completa il 31 luglio 2021. [Ulteriori informazioni](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md)

Origini dati supporta le variabili seguenti durante l&#39;elaborazione dei dati come chiamata server standard (Generic (Generico) > Full Processing (Elaborazione completa)).

I dati di origini dati Elaborazione completa vengono elaborati come se fossero stati ricevuti dai server Adobe al momento specificato (ogni hit contiene una marca temporale).

* [Profilo visitatore](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [Riferimento colonna](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## Profilo visitatore {#section_6065627D0C144506965F562C80AE67F8}

I dati di origini dati Elaborazione completa vengono elaborati utilizzando profili visitatore separati, così anche se l&#39;ID visitatore nei dati caricati corrisponde ai dati raccolti tramite JavaScript o un&#39;altra libreria AppMeasurement, i profili visitatore non sono collegati da un punto di vista di allocazione eVar.

Ad esempio, un utente con un ID visitatore `"user@example.com"` visita il sito da una campagna di marketing denominata &quot;Vendita di primavera&quot;, memorizzata nella variabile della campagna. Se in seguito carichi una transazione utilizzando lo stesso ID visitatore, la campagna &quot;Vendita di primavera&quot; non riceve credito per eventuali ricavi o eventi di successo caricati utilizzando le origini dati di elaborazione completa.

## Riferimento colonna {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile JavaScript </th> 
   <th colname="col2" class="entry"> Variabile colonna Elaborazione completa </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campagna </p> </td> 
   <td colname="col2"> <p>campagna </p> </td> 
   <td colname="col3"> <p>Codice di tracciamento campagna di conversione </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>channel </p> </td> 
   <td colname="col2"> <p>canale </p> </td> 
   <td colname="col3"> <p>Stringa canale (ad esempio, sezione Sport). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>Nota:  Questa variabile è supportata anche dalle origini dati Standard come <code> currency code </code>. </p> </td> 
   <td colname="col3"> <p>Codice valuta ricavi (ad esempio, USD) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timestamp </p> </td> 
   <td colname="col2"> <p>data </p> </td> 
   <td colname="col3"> <p>Utilizzare il formato di data ISO 8601 di <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code> (ad esempio, <code> 2013-09-01T12:00:00-07:00 </code>) o Unix Time Format (il numero di secondi trascorsi dal 1° gennaio 1970). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i>, es. &lt;eVar2&gt;…&lt;/eVar2&gt; </p> </td> 
   <td colname="col3"> <p>Nome eVar conversione. Puoi avere fino a 75 eVar (  <span class="varname"> eVar1  </span> -  <span class="varname"> eVar75  </span>). </p> <p>Puoi specificare il nome eVar (eVar12) o un nome descrittivo (campagna pubblicitaria 3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>events </p> </td> 
   <td colname="col2"> <p>events </p> </td> 
   <td colname="col3"> <p>Stringa Eventi, formattata utilizzando la stessa sintassi della variabile <a href="https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/events/event-serialization.html"  >s.events</a>. </p> <p>Ad esempio: </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i>, es. &lt;hier2&gt;…&lt;/hier2&gt; </p> </td> 
   <td colname="col3"> <p>Nome gerarchia. Puoi avere fino a 5 gerarchie (  <span class="varname"> hier1  </span> -  <span class="varname"> hier5  </span>). </p> <p>È possibile specificare il nome predefinito della gerarchia ( <span class="varname"> hier2 </span>) o un nome descrittivo ( <span class="term"> Yankees </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>Nome del collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>Tipo di collegamento. I valori supportati includono: </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>: collegamento download </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>: collegamento uscita </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>: collegamento personalizzato. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>HREF del collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>Nome pagina </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>Tipo pagina ("Pagina errore"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>URL della pagina (ad esempio, <code>https://www.example.com/index.html)</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>products </p> </td> 
   <td colname="col3"> <p>Elenco prodotti (ad esempio, <code> "Sports;Ball;1;5.95"</code>). Può contenere un valore massimo di 4096 byte per riga.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i>, es. &lt;prop2&gt;…&lt;/prop2&gt; </p> </td> 
   <td colname="col3"> <p>Stringa Property# (ad esempio, <span class="term"> Sezione Sport </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>Numero ID acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>ID suite di rapporti a cui attribuire l'hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server </p> </td> 
   <td colname="col2"> <p>server </p> </td> 
   <td colname="col3"> <p>Stringa Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>stato </p> </td> 
   <td colname="col2"> <p>stato </p> </td> 
   <td colname="col3"> <p>Stringa Stato di conversione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>Codice zip di conversione. </p> </td> 
  </tr> 
 </tbody> 
</table>

La tabella seguente contiene le variabili di traffico inserite automaticamente quando si utilizzano le librerie JavaScript. Queste proprietà non hanno variabili associate ma possono essere importate utilizzando le origini dati.

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variabile colonna Elaborazione completa </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>Altezza browser in pixel (ad esempio, 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>Larghezza browser in pixel (ad esempio, 1024). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>Set di caratteri supportato per il sito Web. Ad esempio, UTF-8, ISO-8859-1 e così via. </p> <p>Consulta il white paper <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/configuration-variables.html#concept_E65B9A8F75C3482C87D0D455805F89BD"  >Set di caratteri multibyte</a> (Internazionalizzazione) per un elenco completo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>Identificatore oggetto per mappa clic visitatore (oid). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>Identificatore oggetto per mappa clic visitatore (oidt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>Identificatore pagina per mappa clic visitatore (pid). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>Identificatore pagina per mappa clic visitatore (pidt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>Indice origine per mappa clic visitatore (oi). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>Nome tag oggetto per mappa clic visitatore (ot). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>Profondità colore monitor in bit (ad esempio, 24). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>Tipo di connessione del visitatore (  <span class="term"> lan  </span> o  <span class="term"> modem  </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>S o N se il visitatore supporta i cookie di sessione di prima parte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>Codice valuta predefinito utilizzato sul sito web. </p> <p>Ad esempio, USD=dollari statunitensi, EUR = Euro, JPY = Yen giapponese, ecc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>S o N se la pagina corrente è la pagina iniziale del visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>S o N se il visitatore ha abilitato Java. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>Versione JavaScript (ad esempio, 1.3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>Elenco separato da punto e virgola dei nomi di plug-in del browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>Valori proprietà per le proprietà. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referrer </p> </td> 
   <td colname="col2"> <p>URL per referente pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>Risoluzione del monitor (ad esempio, 1024x768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>Numero versione richiesta XML rapporti di marketing (ad esempio 1.0). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timezone </p> </td> 
   <td colname="col2"> <p>Offset fuso orario del visitatore da GMT in ore (ad esempio, -8). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>Numero ID visitatore. </p> </td> 
  </tr> 
 </tbody> 
</table>
