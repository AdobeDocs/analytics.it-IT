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


# pageName

La variabile contiene il nome di ogni pagina del sito.

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> 100 byte </td> 
   <td> pageName </td> 
   <td> <p>Pagine </p> <p>Paths (Percorsi) </p> </td> 
   <td> URL pagina </td> 
  </tr> 
 </tbody> 
</table>

La *`pageName`* variabile deve essere compilata con un valore riconosciuto dagli utenti aziendali. Nella maggior parte dei casi, il *`pageName`* valore non è l'URL o il percorso del file. I *`pageName`* valori comuni includono nomi come "Home Page", "Checkout", "Purchase Thank you" (Grazie all’acquisto) o "Registration" (Registrazione).

Prestate attenzione a non consentire la visualizzazione di trattini di nuova riga, -em o -en, né di eventuali caratteri HTML nel nome della pagina e in altre variabili. Alcuni browser inviano nuovi caratteri di riga mentre altri no, causando la divisione dei dati in Analytics tra due nomi di pagina apparentemente identici. Molti elaboratori di testi e client di posta elettronica convertono automaticamente un trattino in un trattino -en o -em durante la digitazione. Poiché i trattini -en e -em sono caratteri non validi nelle variabili di Analytics (caratteri ASCII con codici superiori a 127), Analytics non registra il nome della pagina contenente il carattere non valido e mostra l'URL.

Se *`pageName`* viene lasciato vuoto, l’URL viene utilizzato per rappresentare il nome della pagina. Lasciare *`pageName`* vuoto è spesso problematico perché l’URL potrebbe non essere sempre lo stesso per una pagina `www.mysite.com` e `mysite.com` corrispondere a una pagina con URL diversi).

**Sintassi e valori** possibili {#section_7A61EE70F1A84D26B414404998C84BA8}

La *`pageName`* variabile deve contenere un identificatore utile per gli utenti aziendali di Analytics.

```js
s.pageName="page_name"
```

Non esistono limitazioni *`pageName`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Impostazioni** di configurazione {#section_58CBC68C805344A999EB47455FEBA8D5}

Gli amministratori possono modificare il nome della pagina visibile in Analytics con lo [!UICONTROL Name Pages] strumento, che è potenzialmente pericoloso e può influire negativamente sui rapporti. Contatta l'Assistenza clienti Adobe prima di utilizzare lo [!UICONTROL Name Pages] strumento.

**Insidie, domande e suggerimenti**{#section_BB41DC9682C34385B9CAA80D5257C113}

Assicurarsi che *`pageName`* non contenga caratteri non validi.
