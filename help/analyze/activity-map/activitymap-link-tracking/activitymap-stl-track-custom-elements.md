---
title: Utilizzare il metodo tl() con Activity Map
description: Puoi utilizzare il metodo tl() per tenere traccia degli elementi personalizzati e configurare il rendering di sovrapposizione per il contenuto dinamico.
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 1%

---

# Utilizzare il metodo `tl()` con Activity Map

Puoi utilizzare il metodo `tl()` per tenere traccia degli elementi personalizzati e configurare il rendering di sovrapposizione per il contenuto dinamico.

## Tracciamento degli elementi personalizzati

L&#39;utilizzo del metodo [`tl()`](/help/implement/vars/functions/tl-method.md) come parte del modulo Activity Map AppMeasurement consente di tenere traccia di qualsiasi oggetto su cui si fa clic, anche di oggetti che non sono tag di ancoraggio o elementi immagine. Utilizzando `tl()`, puoi tenere traccia di tutti gli elementi personalizzati che non si traducono in un caricamento di pagina.

Nel metodo `tl()` , il parametro `linkName` attualmente utilizzato per identificare i collegamenti di uscita, i collegamenti personalizzati, ecc. viene ora utilizzato anche per identificare l’ID collegamento per la variabile Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

In altre parole, se utilizzi `tl()` per tracciare gli elementi personalizzati, l’ID del collegamento viene estratto dal valore passato come terzo parametro (Nome collegamento) nel metodo `tl()` . Non viene prelevato dall&#39;algoritmo di tracciamento dei collegamenti standard utilizzato per [il tracciamento predefinito](activitymap-link-tracking-methodology.md) in Activity Map.

## Rendering di sovrapposizione per il contenuto dinamico

Quando il metodo `tl()` viene chiamato direttamente dall’evento on-click dell’elemento HTML, Activity Map può visualizzare una sovrapposizione per tale elemento quando la pagina web viene caricata. Esempio:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Ogni volta che un contenuto di una pagina web viene aggiunto alla pagina dopo il caricamento iniziale della pagina, il metodo `tl()` viene chiamato indirettamente e non è possibile visualizzare sovrapposizioni per quel nuovo contenuto a meno che non venga espressamente attivato/fatto clic su di esso. Quindi viene attivato un nuovo processo di raccolta dei collegamenti da Activity Map.

Quando il metodo `tl()` non viene chiamato direttamente dall’evento on-click dell’elemento HTML, Activity Map può visualizzare la sovrapposizione solo dopo che l’utente ha fatto clic su di esso. Ecco un esempio in cui il metodo `tl()` viene chiamato indirettamente:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Il modo migliore per sovrapporre i collegamenti ai contenuti dinamici in Activity Map consiste nell’impostare una funzione `ActivityMap.link` personalizzata per chiamare la stessa funzione il cui valore restituito viene passato a `tl()`. Ad esempio:

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

In questo caso, abbiamo bypassato la funzione `ActivityMap.link` per eseguire una delle tre operazioni quando viene chiamata:

1. Se viene passato `linkName`, questo è stato chiamato da `tl()`, quindi è sufficiente restituire ciò che `tl()` ha passato come `linkName`.
2. Quando viene chiamato da Activity Map al momento della generazione del rapporto, non viene mai passato un `linkName` e quindi invoca `makeLinkName()` con l’elemento di collegamento. Questo è il passaggio cruciale qui - la chiamata `makeLinkName(element)` deve essere lo stesso argomento del terzo argomento della chiamata `tl()` nel tag `<button>` . Ciò significa che, quando si chiama `tl()`, si tiene traccia della stringa restituita da `makeLinkName()`. Quando Activity Map crea rapporti sui collegamenti presenti nella pagina, utilizza la stessa chiamata per effettuare un collegamento.
3. La soluzione finale è quella di restituire il valore originale della funzione di collegamento ActivityMap predefinita. Mantenere questo riferimento intorno alla chiamata nel caso predefinito ti aiuta a sovrascrivere o scrivere solo codice personalizzato per `makeLinkName()` e a non dover trovare un valore di ritorno del collegamento per tutti i collegamenti sulla pagina.
