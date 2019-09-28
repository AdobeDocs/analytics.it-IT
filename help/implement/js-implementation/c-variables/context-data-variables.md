---
description: Le variabili di dati di contesto consentono di definire variabili personalizzate su ogni pagina che possono essere lette dalle regole di elaborazione.
keywords: Implementazione di Analytics;contextdata;s.contextdata
seo-description: Le variabili di dati di contesto consentono di definire variabili personalizzate su ogni pagina che possono essere lette dalle regole di elaborazione.
seo-title: Variabili di dati di contesto
solution: Analytics
subtopic: Variabili
title: Variabili di dati di contesto
topic: Sviluppatore e implementazione
uuid: 4b215803-99d4-46f2-b3c1-e7858987764
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Variabili di dati di contesto

Le variabili di dati di contesto consentono di definire variabili personalizzate su ogni pagina che possono essere lette dalle regole di elaborazione.

Invece di assegnare in modo esplicito valori a prop ed eVar nel codice, potete inviare dati in variabili di dati di contesto mappate utilizzando le regole di elaborazione. Le regole di elaborazione forniscono una potente interfaccia grafica per apportare modifiche ai dati durante la ricezione. In base ai valori inviati nei dati contestuali, è possibile impostare eventi, copiare valori in eVar e prop ed eseguire istruzioni condizionali aggiuntive.

>[!NOTE]
>
>Le variabili di dati di contesto non fanno distinzione tra maiuscole e minuscole. Ad esempio, le due variabili seguenti sono effettivamente identiche:        &gt;
>```>
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>
>
```>
>and 
>
>
```>
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```>



L'utilizzo dei dati contestuali consente di evitare di eseguire aggiornamenti del codice per supportare diverse configurazioni delle suite di rapporti.

Ad esempio, puoi definire la seguente *`s.contextData`* variabile:

```
s.contextData['myco.rsid'] = 'value'
```

Utilizzando le regole di elaborazione è possibile aggiungere una condizione che verifica la presenza di una variabile di dati di `myco.rsid` contesto. Una volta trovata questa variabile, puoi aggiungere un'azione per copiarla in una prop o eVar.

Le variabili di dati di contesto possono essere definite direttamente nell'interfaccia delle regole di elaborazione per memorizzare temporaneamente un valore, o per raccogliere valori da una variabile di dati di contesto che sai verrà utilizzata nella suite di rapporti. Ad esempio, se è necessario scambiare due valori, è possibile creare una variabile di dati di contesto per memorizzare un valore durante lo scambio.

Poiché le regole di elaborazione vengono applicate solo quando i dati vengono raccolti, è importante impostare le regole di elaborazione prima di iniziare a inviare i dati contestuali. I valori dei dati di contesto che non vengono letti dalle regole di elaborazione quando un hit viene elaborato vengono scartati.

## Regole {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Regola </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nomi e caratteri supportati </p> </td> 
   <td colname="col2"> <p>I nomi delle variabili di dati di contesto possono contenere solo caratteri alfanumerici, caratteri di sottolineatura e punti. Eventuali caratteri aggiuntivi vengono rimossi. Le variabili di contesto non hanno una designazione numerica. Piuttosto, si chiamano. </p> <p>Ad esempio, la variabile di dati contestuali <code> login_page-home </code> diventa automaticamente <code> login_pagehome </code>. Tutti i dati inviati alla variabile <code> login_page-home </code> vengono allocati in <code> login_pagehome </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Namespace </p> </td> 
   <td colname="col2"> <p>È buona norma inserire il prefisso delle variabili con il nome della società, il nome del sito o un valore simile per essere certi che il nome sia univoco nella suite di rapporti. </p> <p>Le variabili di dati di contesto possono essere denominate in modo simile ad altre variabili JavaScript. Lo spazio nomi <code> a.* </code> è riservato ai prodotti Adobe nei nomi delle variabili di contesto. Ad esempio, la libreria AppMeasurement per iOS utilizza <code> a.InstallEvent </code> per misurare le installazioni dell'applicazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limiti URL per Internet Explorer </p> </td> 
   <td colname="col2"> <p>Potrebbe verificarsi una precedente limitazione URL per Internet Explorer 6 e 7, dove gli URL vengono troncati a 2000 byte. È possibile utilizzare il debugger <span class="keyword"> Digital Pulse </span> per determinare la dimensione di una stringa URL. </p> <p>Con i recenti aggiornamenti ad AppMeasurement (settembre 2014), HTTP POST è utilizzato con Internet Explorer 8+, il che elimina i problemi di troncamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione AppMeasurement supportata </p> </td> 
   <td colname="col2"> <p>Le variabili di dati di contesto richiedono almeno il codice H23 o superiore. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Invio di dati contestuali su una chiamata di tracciamento collegamento {#section_35EBE5D1CF29427598BD4B2165CE64FC}

Includi `ContextData` + il nome della variabile da includere in `s.linkTrackVars`:

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## Esempi {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possibili modi per sostituire l'implementazione della *`s.pageName`* variabile, partendo dal presupposto che le regole di elaborazione siano impostate correttamente per ciascuno di essi:

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

Altri esempi per implementare le variabili dei dati di contesto:

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

Per un esempio, vedi [Copiare una variabile di dati di contesto in una eVar](https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_copy_context_data.html) in Analytics Reference.
