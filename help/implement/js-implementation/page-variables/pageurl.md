---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# pageURL

La variabile sostituisce l’URL effettivo della pagina.

<!-- 

pageURL.xml

 -->

In alcuni rari casi, l’URL della pagina non è l’URL da includere nei rapporti in Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessun limite* </td> 
   <td> <p>G </p> </td> 
   <td> Traffico &gt; Segmentazione &gt; Percorsi delle pagine più comuni </td> 
   <td> URL della pagina </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Anche se Adobe consente *`pageURL`* valori fino a 64 k, alcuni browser impongono un limite di dimensione all’URL delle richieste di immagini. Per evitare il troncamento di altri dati, gli URL di pagina di lunghezza superiore a 255 byte vengono suddivisi, con i primi 255 byte visualizzati nel `g=` parametro, con i rimanenti byte che vengono visualizzati successivamente nella stringa di query nel parametro della `-g=` query.

**Sintassi e valori** possibili {#section_22AF3BF7C2F743549967B0C760A095C0}

La *`pageURL`* variabile deve essere un URL valido, con un protocollo valido. Il dominio verrà forzato a essere visualizzato in lettere minuscole prima di essere popolato nei report, e la stringa di query potrebbe essere rimossa, a seconda delle impostazioni di Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

Solo i caratteri compatibili con l’URL sono consentiti come URL della pagina.

> [!NOTE] Prima di utilizzare la *`pageURL`* variabile per scopi personalizzati, si consiglia vivamente di contattare il consulente Adobe o l'Assistenza clienti.

**Esempi** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Impostazioni** di configurazione {#section_A8F77DAD88164528ACC5C16C066B47DF}

Nessuno

