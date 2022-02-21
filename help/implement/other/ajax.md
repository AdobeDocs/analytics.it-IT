---
title: Implementazione con AJAX
description: Scopri come implementare Adobe Analytics su un sito utilizzando AJAX.
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---

# Implementazione con AJAX

AJAX è una pratica di utilizzare JavaScript e HTML per cancellare e generare contenuto senza caricare una nuova pagina.

Adobe Analytics normalmente si basa sul ricaricamento delle pagine per reimpostare l&#39;oggetto di tracciamento di Analytics. Ogni volta che accedi a un URL diverso, tutte le variabili di Analytics vengono reimpostate e possono essere definite di nuovo. Quando utilizzi AJAX sul sito, regola l’implementazione in caso di mancanza di aggiornamenti di pagina per evitare che i dati persistano in modo errato tra gli hit.

Una volta adottate le misure per cancellare i valori delle variabili, l’implementazione di Adobe Analytics sui siti che utilizzano AJAX è principalmente identica ad altri metodi di implementazione.

## Determinazione delle interazioni e dei tipi di hit

Poiché le pagine che utilizzano AJAX in genere non vengono ricaricate, un utente può interagire più volte sul sito. Quando implementi Adobe Analytics, accertati di distinguere le visualizzazioni di pagina dalle chiamate di tracciamento dei collegamenti. Considera la seguente domanda per ogni interazione che un utente può intraprendere sul tuo sito:

*Quando un utente interagisce con il mio sito, tale interazione cambia abbastanza del contenuto della pagina per qualificarsi come nuova pagina?*

* Se la risposta è **sì**, considera l&#39;utilizzo di una chiamata di tracciamento della visualizzazione di una pagina (`s.t()`).
* Se la risposta è **no**, considera il tracciamento di tale interazione utilizzando una chiamata di tracciamento dei collegamenti (`s.tl()`).

>[!NOTE]
>
>Non è necessario registrare tutte le interazioni o i clic. Considera attentamente le azioni più importanti da monitorare e invia i dati ad Adobe di conseguenza.

## Cancellazione delle variabili in ogni pagina

I valori delle variabili persistono sulle pagine che utilizzano AJAX poiché la pagina non viene ricaricata. Pertanto, è necessario un alloggio speciale per cancellare i valori delle variabili in modo che non persistano in modo errato tra gli hit. L’Adobe offre [`clearVars`](../vars/functions/clearvars.md) per cancellare facilmente i valori delle variabili. Assicurati di utilizzare questa funzione dopo aver inviato ogni hit ad Adobe e prima di impostare i valori delle variabili per l&#39;hit successivo.

>[!TIP]
>
>La `clearVars()` La funzione non è disponibile in H Code. Se non hai effettuato l’aggiornamento ad AppMeasurement, imposta ogni valore di variabile Analytics su una stringa vuota.

## Esempi

Nell&#39;esempio seguente viene utilizzato un semplice JavaScript per cancellare i valori delle variabili esistenti, impostare nuovi valori e inviare ad Adobe una richiesta di immagine:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

L’esempio seguente mostra una chiamata di tracciamento nel `done` callback di JQuery `.ajax` funzione:

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
