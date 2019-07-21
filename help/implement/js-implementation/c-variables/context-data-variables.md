---
description: Le variabili di dati di contesto ti permettono di definire variabili personalizzate su ogni pagina che possono essere lette mediante regole di elaborazione.
keywords: Implementazione di Analytics; contextdata; s. contextdata
seo-description: Le variabili di dati di contesto ti permettono di definire variabili personalizzate su ogni pagina che possono essere lette mediante regole di elaborazione.
seo-title: Variabili di dati di contesto
solution: Analytics
subtopic: Variabili
title: Variabili di dati di contesto
topic: Sviluppatore e implementazione
uuid: 4 b 215803-99 d 4-46 f 2-b 3 c 1-e 78558987764
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Variabili di dati di contesto

Le variabili di dati di contesto ti permettono di definire variabili personalizzate su ogni pagina che possono essere lette mediante regole di elaborazione.

Invece di assegnare esplicitamente valori a prop ed evar nel codice, puoi inviare dati nelle variabili dati di contesto mappate utilizzando le regole di elaborazione. Le regole di elaborazione offrono un'efficace interfaccia grafica che consente di apportare modifiche ai dati durante la ricezione. In base ai valori inviati nei dati contestuali, potete impostare eventi, copiare valori in evar e prop ed eseguire ulteriori istruzioni condizionali.

>[!NOTE]
>
>Le variabili di dati di contesto non fanno distinzione tra maiuscole e minuscole. Ad esempio, le seguenti variabili 2 sono identiche: &gt;
>```>
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>
>```>
>and 
>
>```>
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```>



L'utilizzo dei dati contestuali aiuta a evitare di creare aggiornamenti di codice per supportare configurazioni diverse di suite di rapporti.

For example, you can define the following *`s.contextData`* variable:

```
s.contextData['myco.rsid'] = 'value'
```

Using processing rules you can add a condition that checks for a `myco.rsid` context data variable. Quando viene trovata questa variabile, puoi aggiungere un'azione per copiarla in una prop o evar.

Le variabili di dati di contesto possono essere definite direttamente nell'interfaccia delle regole di elaborazione per memorizzare temporaneamente un valore, oppure per raccogliere valori da una variabile di dati contestuali che sai verrà utilizzata nella suite di rapporti. Ad esempio, se devi sostituire due valori, puoi creare una variabile di dati di contesto per memorizzare un valore durante l'swap.

Poiché le regole di elaborazione vengono applicate solo quando vengono raccolti dati, è importante configurare le regole di elaborazione prima di iniziare a inviare i dati contestuali. I valori dei dati contestuali che non sono letti dalle regole di elaborazione quando un hit viene elaborato vengono eliminati.

## Rules {#section_2229739F6B1A4C1CAD7140BDF4687523}

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
   <td colname="col2"> <p>I nomi di variabile dati contestuali possono contenere solo caratteri alfanumerici, caratteri di sottolineatura e punti. Vengono rimossi eventuali caratteri aggiuntivi. Le variabili di contesto di contesto non hanno una designazione numerica. Vengono invece denominati. </p> <p>For example, the context data variable <code> login_page-home </code> automatically becomes <code> login_pagehome </code>. All data sent to the <code> login_page-home </code> variable is allocated under <code> login_pagehome </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Namespace </p> </td> 
   <td colname="col2"> <p>È buona norma prefisso le variabili con il nome della tua società, il nome del sito o un valore simile per fare in modo che il nome sia univoco nella tua suite di rapporti. </p> <p>Le variabili di dati di contesto possono essere denominate simili ad altre variabili javascript. Be aware that the namespace <code> a.* </code> is reserved for use by Adobe products in context variable names. For example, the AppMeasurement Library for iOS uses <code> a.InstallEvent </code> to measure application installations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limiti URL per Internet Explorer </p> </td> 
   <td colname="col2"> <p>Potrebbe verificarsi una limitazione di URL precedente per Internet Explorer 6 e 7, dove gli URL vengono troncati a 2000 byte. You can use the <span class="keyword"> DigitalPulse </span> debugger to determine the size of a URL string. </p> <p>Con gli aggiornamenti recenti ad appmeasurement (2014 settembre), HTTP POST viene usato con Internet Explorer 8 +, che elimina problemi di troncamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione appmeasurement supportata </p> </td> 
   <td colname="col2"> <p>Le variabili di dati di contesto richiedono almeno il codice H 23 o superiore. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sending Context Data on a Track Link Call {#section_35EBE5D1CF29427598BD4B2165CE64FC}

Include `ContextData` + the name of the variable that you would like included in `s.linkTrackVars`:

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## Esempi {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possible ways to replace implementation of the *`s.pageName`* variable, assuming that processing rules are set up correctly for each:

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

Altri esempi per implementare le variabili di dati di contesto:

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

For an example, see [Copy a Context Data Variable to an eVar](https://marketing.adobe.com/resources/help/en_US/reference/?f=processing_rules_copy_context_data) in Analytics Reference.
