---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkTrackEvents

La variabile è un elenco separato da virgole di eventi inviati con un [!UICONTROL custom], [!UICONTROL exit]o [!UICONTROL download] collegamento.

Se un evento non si trova in *`linkTrackEvents`*, non viene inviato a [!DNL Analytics], anche se viene popolato in [!UICONTROL onClick] caso di collegamento, come illustrato nell'esempio seguente:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

Nel primo collegamento a [!DNL help.php], la variabile degli eventi mantiene il valore impostato prima che sia fatto clic sul collegamento. Questo consente di inviare event1 con il collegamento personalizzato. Nel secondo esempio, il collegamento a [!DNL test.php], event2 non viene registrato perché non è elencato in *`linkTrackEvents`*.

Per evitare confusione e potenziali problemi, Adobe consiglia di compilare *`linkTrackVars`* e *`linkTrackEvents`* nel [!UICONTROL onClick] caso di un collegamento utilizzato per il tracciamento dei collegamenti.

La *`linkTrackEvents`* variabile contiene gli eventi da inviare con [!UICONTROL custom], [!UICONTROL download]e [!UICONTROL exit] i collegamenti. Questa variabile viene considerata solo se *`linkTrackVars`* contiene "events".

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Conversione | "Nessuno" |

## Sintassi e valori possibili

La *`linkTrackEvents`* variabile è un elenco di eventi separati da virgole (senza spazi).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

In *`linkTrackEvents`*. Questi eventi sono elencati in [Eventi](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Se uno spazio compare prima o dopo il nome dell’evento, l’evento non può essere inviato con richieste di immagini di collegamento.

## Esempi

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* Il file JavaScript viene utilizzato solo *`linkTrackEvents`* se *`linkTrackVars`* contiene la variabile "events". "events" deve essere incluso *`linkTrackVars`* solo quando *`linkTrackEvents`* è definito.

* Attenzione se un evento viene attivato su una pagina ed è elencato in *`linkTrackEvents`*. Tale evento viene registrato nuovamente con eventuali [!UICONTROL exit], [!UICONTROL download]o [!UICONTROL custom] collegamenti, a meno che la variabile degli eventi non venga reimpostata prima di tale evento (in [!UICONTROL onClick] un collegamento o dopo la chiamata alla *`t()`* funzione).

* Se *`linkTrackEvents`* contiene spazi tra i nomi degli eventi, gli eventi non vengono registrati.
