---
title: Implementazione con AJAX
description: Scopri come implementare Adobe Analytics su un sito utilizzando l’AJAX.
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---

# Implementazione con AJAX

L’AJAX prevede l’utilizzo di JavaScript e HTML per cancellare e generare contenuti senza caricare una nuova pagina.

Adobe Analytics di solito si basa sul ricaricamento delle pagine per ripristinare l’oggetto di tracciamento Analytics. Ogni volta che passi a un URL diverso, tutte le variabili di Analytics vengono reimpostate e possono essere definite di nuovo. Quando utilizzi l’AJAX sul sito, regola l’implementazione in base alla mancanza di aggiornamenti di pagina per assicurarti che i dati non persistano erroneamente tra gli hit.

Una volta implementate le misure per cancellare i valori delle variabili, implementare Adobe Analytics sui siti che utilizzano AJAX è per lo più lo stesso di altri metodi di implementazione.

## Determinazione delle interazioni e dei tipi di hit

Poiché le pagine che utilizzano l’AJAX in genere non vengono ricaricate, un utente può eseguire più interazioni sul sito. Quando implementi Adobe Analytics, accertati di distinguere le visualizzazioni di pagina dalle chiamate di tracciamento dei collegamenti. Per ogni interazione che un utente può eseguire sul sito, considera la seguente domanda:

*Quando un utente interagisce con il sito, l’interazione cambia in misura sufficiente il contenuto della pagina per qualificarsi come nuova pagina?*

* Se la risposta è **sì**, è consigliabile utilizzare una chiamata di tracciamento della visualizzazione pagina (`s.t()`).
* Se la risposta è **no**, considera il tracciamento di tale interazione utilizzando una chiamata di tracciamento dei collegamenti (`s.tl()`).

>[!NOTE]
>
>Non tutte le interazioni o i clic devono essere registrati. Considera attentamente quali azioni sono più importanti da tracciare, e invia i dati agli Adobi di conseguenza.

## Cancellazione delle variabili in ogni pagina

I valori delle variabili persistono nelle pagine che utilizzano l’AJAX poiché la pagina non viene ricaricata. Pertanto, è necessario tenere presente che i valori delle variabili devono essere cancellati in modo che non persistano in modo errato nei diversi hit. Adobe offre [`clearVars`](../vars/functions/clearvars.md) per cancellare facilmente i valori delle variabili. Assicurati di utilizzare questa funzione dopo aver inviato ogni hit all’Adobe e prima di impostare i valori delle variabili per l’hit successivo.

>[!TIP]
>
>Il `clearVars()` non è disponibile nel codice H. Se non hai effettuato l’aggiornamento ad AppMeasurement, imposta ogni valore della variabile di Analytics su una stringa vuota.

## Esempi

L’esempio seguente utilizza JavaScript semplice per cancellare i valori delle variabili esistenti, impostare nuovi valori e inviare una richiesta di immagine all’Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

L’esempio seguente mostra una chiamata di tracciamento nel `done` callback della query JQ `.ajax` funzione:

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```
