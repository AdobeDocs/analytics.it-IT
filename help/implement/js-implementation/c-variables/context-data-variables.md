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
source-git-commit: 959e4963eafe6e32a55b2ce9659fe43ea8086527

---


# Variabili di dati di contesto

Le variabili di dati di contesto consentono di definire variabili personalizzate su ogni pagina che possono essere lette dalle regole di elaborazione.

Invece di assegnare in modo esplicito valori a prop ed eVar nel codice, potete inviare dati in variabili di dati di contesto mappate utilizzando le regole di elaborazione. Le regole di elaborazione forniscono una potente interfaccia grafica per apportare modifiche ai dati durante la ricezione. In base ai valori inviati nei dati contestuali, è possibile impostare eventi, copiare valori in eVar e prop ed eseguire istruzioni condizionali aggiuntive.

>[!NOTE]
>
>Le variabili di dati di contesto non fanno distinzione tra maiuscole e minuscole. Ad esempio, le due variabili seguenti sono effettivamente identiche:
>```
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>```
>e
>```
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```

L'utilizzo dei dati contestuali consente di evitare di eseguire aggiornamenti del codice per supportare diverse configurazioni delle suite di rapporti.

Ad esempio, puoi definire la seguente *`s.contextData`* variabile:

```
s.contextData['myco.rsid'] = 'value'
```

Utilizzando le regole di elaborazione è possibile aggiungere una condizione che verifica la presenza di una variabile di dati di `myco.rsid` contesto. Una volta trovata questa variabile, puoi aggiungere un'azione per copiarla in una prop o eVar.

Le variabili di dati di contesto possono essere definite direttamente nell'interfaccia delle regole di elaborazione per memorizzare temporaneamente un valore, o per raccogliere valori da una variabile di dati di contesto che sai verrà utilizzata nella suite di rapporti. Ad esempio, se è necessario scambiare due valori, è possibile creare una variabile di dati di contesto per memorizzare un valore durante lo scambio.

Poiché le regole di elaborazione vengono applicate solo quando i dati vengono raccolti, è importante impostare le regole di elaborazione prima di iniziare a inviare i dati contestuali. I valori dei dati contestuali che non vengono letti dalle regole di elaborazione quando un hit viene elaborato vengono scartati.

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
   <td colname="col2"> <p>I nomi delle variabili di dati di contesto possono contenere solo caratteri alfanumerici, caratteri di sottolineatura e punti. Eventuali caratteri aggiuntivi vengono rimossi. Context cata variables do not have a numeric designation. Rather, they are named. </p> <p>For example, the context data variable <code> login_page-home </code> automatically becomes <code> login_pagehome </code>. All data sent to the  login_page-home  variable is allocated under  login_pagehome .<code></code><code></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Namespace </p> </td> 
   <td colname="col2"> <p>A good practice is to prefix your variables with your company name, site name, or a similar value to make sure the name is unique across your report suite. </p> <p>Context data variables can be named similar to other JavaScript variables. Lo spazio nomi <code> a.* </code> è riservato ai prodotti Adobe nei nomi delle variabili di contesto. For example, the AppMeasurement Library for iOS uses  a.InstallEvent  to measure application installations.<code></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL Limits for Internet Explorer </p> </td> 
   <td colname="col2"> <p>You might encounter a older URL limitation for Internet Explorer 6 and 7, where URLs are truncated at 2000 bytes. You can use the  DigitalPulse  debugger to determine the size of a URL string.<span class="keyword"></span> </p> <p>With the recent updates to AppMeasurement (September 2014),HTTP POST is used with Internet Explorer 8+, which eliminates truncation issues. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supported AppMeasurement version </p> </td> 
   <td colname="col2"> <p>Context data variables require at least H23 code or higher. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sending Context Data on a Track Link Call {#section_35EBE5D1CF29427598BD4B2165CE64FC}

Includi `ContextData` + il nome della variabile da includere in `s.linkTrackVars`:

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## Esempi {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possible ways to replace implementation of the  variable, assuming that processing rules are set up correctly for each:*`s.pageName`*

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
