---
title: Utilizzare il metodo tl() con Activity Map
description: Puoi utilizzare il metodo tl() per tenere traccia degli elementi personalizzati e configurare il rendering della sovrapposizione per il contenuto dinamico.
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Utilizza il `tl()` metodo con Activity Map

È possibile utilizzare `tl()` metodo per tenere traccia degli elementi personalizzati e configurare il rendering della sovrapposizione per il contenuto dinamico.

## Tracciamento degli elementi personalizzati

Utilizzo di [`tl()` metodo](/help/implement/vars/functions/tl-method.md) come parte del modulo AppMeasurement Activity Map, consente di tenere traccia di qualsiasi oggetto su cui si fa clic, anche di oggetti che non sono tag di ancoraggio o elementi immagine. Utilizzo di `tl()`, puoi tenere traccia di tutti gli elementi personalizzati che non comportano il caricamento di una pagina.

In `tl()` metodo, il `linkName` parametro attualmente utilizzato per identificare i collegamenti di uscita, i collegamenti personalizzati e così via. viene ora utilizzato anche per identificare l’ID collegamento per la variabile Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

In altre parole, se utilizzi `tl()` per tenere traccia degli elementi personalizzati, l’ID del collegamento viene estratto dal valore passato come terzo parametro (nome del collegamento) in `tl()` metodo. Non viene estratto dall’algoritmo di tracciamento dei collegamenti standard utilizzato per [tracciamento predefinito](activitymap-link-tracking-methodology.md) in Activity Map.

## Rendering della sovrapposizione per il contenuto dinamico

Quando `tl()` viene chiamato direttamente dall&#39;evento on-click dell&#39;elemento HTML. Activity Map può visualizzare una sovrapposizione per tale elemento al caricamento della pagina web. Esempio:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Ogni volta che un contenuto di una pagina web viene aggiunto alla pagina dopo il caricamento della pagina iniziale, il `tl()` viene chiamato indirettamente e non è possibile visualizzare sovrapposizioni per il nuovo contenuto a meno che non venga espressamente attivato/fatto clic su di esso. Viene quindi attivato un nuovo processo di raccolta di collegamenti dall’Activity Map.

Quando `tl()` Il metodo non viene chiamato direttamente dall&#39;evento on-click dell&#39;elemento HTML. Activity Map può visualizzare la sovrapposizione solo dopo che l&#39;utente ha fatto clic su tale elemento. Ecco un esempio in cui `tl()` il metodo viene chiamato indirettamente:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Il modo migliore per l’Activity Map per sovrapporre i collegamenti di contenuto dinamico è quello di avere un `ActivityMap.link` funzione impostata per chiamare la stessa funzione il cui valore restituito viene passato a `tl()`. Ad esempio:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

In questo caso, abbiamo ignorato `ActivityMap.link` funzione per eseguire una delle tre operazioni quando chiamato:

1. Se `linkName` è passato, quindi è stato chiamato da `tl()`, quindi restituisci cosa `tl()` passato come `linkName`.
2. Quando viene chiamato dall’Activity Map al momento della generazione del rapporto, viene `linkName` non viene mai passato, quindi chiama `makeLinkName()` con l’elemento link. Questo è il passaggio cruciale: `makeLinkName(element)` la chiamata deve essere uguale alla `tl()` terzo argomento della chiamata in `<button>` tag. Ciò significa che quando `tl()` si chiama, si tiene traccia della stringa restituita da `makeLinkName()`. Quando l’Activity Map crea un rapporto sui collegamenti nella pagina, utilizza la stessa chiamata per creare un collegamento.
3. La soluzione finale consiste nel restituire il valore restituito originale della funzione di collegamento ActivityMap predefinita. Mantenere questo riferimento intorno per chiamare nel caso predefinito ti aiuta a dover solo sovrascrivere o scrivere il codice personalizzato per `makeLinkName()` e di non dover impostare un valore di ritorno per tutti i collegamenti presenti nella pagina.
