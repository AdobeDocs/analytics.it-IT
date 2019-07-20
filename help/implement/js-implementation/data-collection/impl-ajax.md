---
description: L'implementazione con AJAX è esattamente come la distribuzione del codice in una pagina HTML standard.
keywords: Implementazione di Analytics
seo-description: L'implementazione con AJAX è esattamente come la distribuzione del codice in una pagina HTML standard.
seo-title: Implementazione con AJAX
solution: Analytics
title: Implementazione con AJAX
topic: Sviluppatore e implementazione
uuid: 9 e 3477 ef -7 dea -4 c 76-ab 61-36 a 188222 be 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementazione con AJAX

L'implementazione con AJAX è esattamente come la distribuzione del codice in una pagina HTML standard.

L'azienda ha domande che necessitano di risposte, sono state valutate le esigenze e le variabili sono state assegnate. La progettazione viene quindi applicata e distribuita. Questi concetti dovrebbero avere familiarità con le fasi iniziali dell'implementazione.

## Designing the Solution {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

The difference when throwing [!UICONTROL AJAX] into the mix is first understanding the level of detail that needs to be gathered. Il potenziale di modifica del contenuto sulla pagina (livello di macro) o gli attributi di tracciamento dell'applicazione (micro livello) determina quali variabili devono essere impostate e quale metodo di invio dei dati ad Adobe funziona meglio.

## Deploying the Code {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Il codice javascript è dotato di due funzioni che consentono di inviare dati. Esistono alcune linee guida distinte da seguire per sapere quale metodo deve essere utilizzato per inviare i dati.
Se in precedenza è stata effettuata una richiesta di immagine sulla stessa pagina, occorre prima cancellare i valori delle variabili precedentemente impostate. Use the `clearVars()` funtion in [!DNL AppMeasurement] for JavaScript, or write a simple JavaScript function to clear the variables if you are using H code. Set the values appropriate for the changed content, namely the *`pageName`* variable. After the variables are set call the *`t()`* function.

>[!NOTE]
>
>Before you call `s.t()`, you must clear any values on the s object that you do not want to persist. if you are using [!DNL AppMeasurement] for JavaScript, you can call `s.clearVars()`. Se utilizzi il codice H, scrivete una semplice routine per impostare le variabili su una stringa vuota.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 
```

Se in precedenza è stata effettuata una richiesta di immagine sulla stessa pagina, cancellate i valori delle variabili precedentemente impostate. Questo può essere ottenuto mediante:

* Scrittura di una semplice funzione javascript per cancellare le variabili Adobe.
* Set the *`linkTrackVars`* and *`linkTrackEvents`* variables if you have not already done it in the [!DNL s_code.js] file.

* Set the values appropriate for the changed content, namely the *`pageName`* variable.
* After the variables are set, call the *`tl()`* function.

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```

