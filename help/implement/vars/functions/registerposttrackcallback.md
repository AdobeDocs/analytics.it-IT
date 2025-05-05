---
title: registerPostTrackCallback
description: Crea funzioni di callback dopo aver inviato un hit all’Adobe.
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 7%

---

# registerPostTrackCallback

La variabile `registerPostTrackCallback` consente all&#39;organizzazione di eseguire l&#39;hook di una funzione JavaScript immediatamente dopo l&#39;invio di un hit a Adobe. Se una chiamata di tracciamento non riesce, questa funzione non viene eseguita. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un’infrastruttura interna, oppure per pulire i valori delle variabili nelle applicazioni a pagina singola.

>[!WARNING]
>
>Non effettuare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) nella variabile `registerPostTrackCallback`. L’impostazione delle chiamate di tracciamento in questa variabile causa un ciclo infinito di richieste di immagini.

Ogni volta che si chiama la variabile `registerPostTrackCallback`, la funzione viene eseguita immediatamente dopo l&#39;invio di una richiesta di immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>La tempistica e l&#39;ordine delle funzioni attivate tra [`registerPreTrackCallback`](registerpretrackcallback.md) e `registerPostTrackCallback` non sono garantiti. Evita le dipendenze tra queste due funzioni.

## Tracciamento del callback con Post tramite l&#39;estensione Web SDK

In arrivo!

## Post-track Callback implementando manualmente il Web SDK

Puoi utilizzare una promessa JavaScript quando invii un evento per registrare una funzione dopo che i dati sono stati inviati correttamente all’Adobe.

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

Per ulteriori informazioni, consulta [Gestione delle risposte dagli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=it#handling-responses-from-events) nella documentazione di Web SDK.

## Registrare il callback di tracciamento di Post utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.registerPostTrackCallback in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

`s.registerPostTrackCallback` è una funzione che accetta una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente dopo l’invio di una richiesta di immagine.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l&#39;URL della richiesta di immagine nel codice, fai riferimento all&#39;argomento stringa `requestUrl` nella funzione nidificata. È possibile analizzare la variabile `requestUrl` per l&#39;uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Argomenti aggiuntivi possono essere inclusi nella funzione `s.registerPostTrackCallback`, che può essere utilizzata nella funzione nidificata:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Caso d’uso

La registrazione della funzione [`clearVars()`](clearvars.md) nel callback di post-tracciamento può essere utile per le applicazioni a pagina singola. Ogni volta che si invia un hit all&#39;Adobe, viene eseguita la funzione `clearVars()`. L’implementazione può quindi definire nuovamente le variabili senza preoccuparsi di valori persistenti in modo errato.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
