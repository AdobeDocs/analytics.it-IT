---
description: L’implementazione con AJAX è esattamente come la distribuzione del codice su una pagina HTML standard.
keywords: Implementazione di Analytics
seo-description: L’implementazione con AJAX è esattamente come la distribuzione del codice su una pagina HTML standard.
seo-title: Implementazione con AJAX
solution: Analytics
title: Implementazione con AJAX
topic: Sviluppatore e implementazione
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Implementazione con AJAX

L’implementazione con AJAX è esattamente come la distribuzione del codice su una pagina HTML standard.

L'azienda ha domande che necessitano di risposte, le esigenze vengono valutate e le variabili assegnate. La progettazione viene quindi applicata e implementata. Questi concetti dovrebbero essere familiari se hai già attraversato le fasi iniziali di implementazione.

## Progettazione della soluzione {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

La differenza quando si passa [!UICONTROL AJAX] al mix è innanzitutto capire il livello di dettaglio che occorre raccogliere. La possibilità di modificare il contenuto della pagina (livello macro) o gli attributi di tracciamento dell’applicazione (livello micro) determina quali variabili devono essere impostate e quale metodo di invio dei dati ad Adobe funziona meglio.

## Distribuzione del codice {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Nel codice JavaScript sono presenti due funzioni che consentono di inviare i dati. Esistono alcune linee guida distinte da seguire per sapere quale metodo deve essere utilizzato per inviare i dati.
Se una richiesta di immagine è stata precedentemente effettuata sulla stessa pagina, è innanzitutto necessario cancellare i valori delle variabili impostate in precedenza. Utilizzare la `clearVars()` funzione in [!DNL AppMeasurement] per JavaScript, oppure scrivere una semplice funzione JavaScript per cancellare le variabili se si utilizza il codice H. Impostate i valori appropriati per il contenuto modificato, ovvero la *`pageName`* variabile. Dopo l'impostazione delle variabili, chiamare la *`t()`* funzione.

> [!NOTE] Prima di chiamare `s.t()`, è necessario cancellare tutti i valori sull'oggetto s che non si desidera mantenere. se utilizzate [!DNL AppMeasurement] per JavaScript, potete chiamare `s.clearVars()`. Se si utilizza il codice H, scrivere una semplice routine per impostare le variabili su una stringa vuota.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

L'esempio seguente mostra una chiamata di tracciamento nel `done` callback della funzione JQuery `.ajax` :

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

Se una richiesta di immagine è stata precedentemente effettuata sulla stessa pagina, cancellare i valori delle variabili impostate in precedenza. A tal fine:

* Scrittura di una semplice funzione JavaScript per cancellare le variabili Adobe.
* Impostate le variabili *`linkTrackVars`* e *`linkTrackEvents`* se non lo avete già fatto nel [!DNL s_code.js] file.

* Impostate i valori appropriati per il contenuto modificato, ovvero la *`pageName`* variabile.
* Dopo aver impostato le variabili, chiamare la *`tl()`* funzione.

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

