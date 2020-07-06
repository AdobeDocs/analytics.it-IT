---
title: Implementazione con AJAX
description: Scoprite come implementare Adobe  Analytics in un sito utilizzando AJAX.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---


# Implementazione con AJAX

AJAX è una pratica di utilizzo di JavaScript e HTML per cancellare e generare contenuto senza caricare una nuova pagina.

Adobe  Analytics utilizza normalmente le pagine che si ricaricano per ripristinare l&#39;oggetto di tracciamento  Analytics. Ogni volta che andate a un URL diverso, tutte  variabili Analytics vengono reimpostate e possono essere definite di nuovo. Quando usi AJAX sul tuo sito, regola la tua implementazione in caso di mancanza di aggiornamenti di pagina per assicurarsi che i dati non persistano in modo errato tra gli hit.

Una volta adottate le misure per cancellare i valori delle variabili, l&#39;implementazione di Adobe  Analytics in siti che utilizzano AJAX è in gran parte identica ad altri metodi di implementazione.

## Determinazione delle interazioni e dei tipi di hit

Poiché le pagine che utilizzano AJAX in genere non vengono ricaricate, l&#39;utente può interagire più volte sul sito. Quando implementate Adobe  Analytics, accertatevi di distinguere le visualizzazioni di pagina dalle chiamate per il tracciamento dei collegamenti. Considerate la seguente domanda per ogni interazione che un utente può effettuare sul sito:

*Quando un utente interagisce con il sito, tale interazione cambia abbastanza del contenuto della pagina per qualificarsi come nuova pagina?*

* Se la risposta è **sì**, provate a usare una chiamata di tracciamento visualizzazione pagina (`s.t()`).
* Se la risposta **non**&#x200B;è soddisfacente, tieni in considerazione il tracciamento di tale interazione mediante una chiamata di tracciamento dei collegamenti (`s.tl()`).

>[!NOTE]
>
>Non tutte le interazioni o i clic devono essere registrati. Considera attentamente quali azioni sono più importanti per monitorare e inviare i dati ad Adobe di conseguenza.

## Cancellazione delle variabili in ogni pagina

I valori delle variabili persistono sulle pagine che utilizzano AJAX poiché la pagina non viene ricaricata. Pertanto, per cancellare i valori delle variabili è necessario disporre di una sistemazione speciale in modo che non persistano in modo errato tra gli hit. Adobe offre la [`clearVars`](../vars/functions/clearvars.md) funzione di cancellare facilmente i valori variabili. Accertatevi di utilizzare questa funzione dopo aver inviato ogni hit ad Adobe e prima di impostare i valori variabili per l’hit successivo.

>[!TIP]
>
>La `clearVars()` funzione non è disponibile in H Code. Se non avete effettuato l’aggiornamento ad AppMeasurement, impostate ogni  valore di variabile Analytics su una stringa vuota.

## Esempi

L&#39;esempio seguente utilizza un semplice JavaScript per cancellare i valori delle variabili esistenti, impostare nuovi valori e inviare una richiesta di immagine ad Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

L&#39;esempio seguente mostra una chiamata di tracciamento nel `done` callback della funzione JQuery `.ajax` :

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
