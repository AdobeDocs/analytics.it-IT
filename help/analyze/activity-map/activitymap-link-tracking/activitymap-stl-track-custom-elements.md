---
title: Utilizzate il metodo tl() con  Activity Map
description: Potete usare il metodo tl() per tenere traccia degli elementi personalizzati e per configurare il rendering delle sovrapposizioni per il contenuto dinamico.
topic: Activity Map
translation-type: tm+mt
source-git-commit: 65cb0a49ef74156f0b8adf4a11c6fec6394d306f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 1%

---


# Utilizzare il metodo `tl()` con  Activity Map

Potete utilizzare il metodo `tl()` per tenere traccia degli elementi personalizzati e configurare il rendering delle sovrapposizioni per il contenuto dinamico.

## Tracciamento di elementi personalizzati

L&#39;utilizzo del metodo [`tl()`](/help/implement/vars/functions/tl-method.md) come parte del modulo AppMeasurement  Activity Map consente di tenere traccia di qualsiasi oggetto su cui si fa clic, anche degli oggetti che non sono tag di ancoraggio o elementi immagine. Utilizzando `tl()`, potete tenere traccia di qualsiasi elemento personalizzato che non si traduca in un caricamento di pagina.

Nel metodo `tl()`, il parametro `linkName` attualmente utilizzato per identificare i collegamenti di uscita, i collegamenti personalizzati e così via. viene ora utilizzato anche per identificare l’ID collegamento per la variabile Activity Map .

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

In altre parole, se utilizzate `tl()` per tenere traccia degli elementi personalizzati, l&#39;ID collegamento viene estratto dal valore passato come terzo parametro (nome collegamento) nel metodo `tl()`. Non viene estratto dall&#39;algoritmo di tracciamento dei collegamenti standard utilizzato per il monitoraggio [predefinito](activitymap-link-tracking-methodology.md) nel Activity Map .

## Rendering delle sovrapposizioni per il contenuto dinamico

Quando il metodo `tl()` viene chiamato direttamente dall&#39;evento on-click dell&#39;elemento HTML,  Activity Map può visualizzare una sovrapposizione per tale elemento quando la pagina Web viene caricata. Esempio:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Ogni volta che un contenuto di una pagina Web viene aggiunto alla pagina dopo il caricamento iniziale della pagina, il metodo `tl()` viene chiamato indirettamente e non è possibile visualizzare sovrapposizioni per tale nuovo contenuto a meno che non sia espressamente attivato o fatto clic su di esso. Quindi viene avviato un nuovo processo di raccolta dei collegamenti da  Activity Map.

Quando il metodo `tl()` non viene chiamato direttamente dall&#39;evento on-click dell&#39;elemento HTML,  Activity Map può visualizzare la sovrapposizione solo dopo che l&#39;utente ha fatto clic su di esso. Di seguito è riportato un esempio in cui il metodo `tl()` viene chiamato indirettamente:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Il modo migliore per  Activity Map per sovrapporre collegamenti di contenuto dinamico consiste nell&#39;impostare una funzione `ActivityMap.link` personalizzata per chiamare la stessa funzione il cui valore restituito è passato a `tl()`. Ad esempio:

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

Qui abbiamo sostituito la funzione `ActivityMap.link` per eseguire una delle tre operazioni richiamate:

1. Se `linkName` viene passato, allora questo è stato chiamato da `tl()`, quindi è sufficiente restituire ciò che `tl()` è passato come `linkName`.
2. Quando viene chiamato da  Activity Map al momento del reporting, un `linkName` non viene mai passato e quindi chiamare `makeLinkName()` con l&#39;elemento link. Questo è il passaggio cruciale: la chiamata `makeLinkName(element)` deve essere la stessa del terzo argomento della chiamata `tl()` nel tag `<button>`. Ciò significa che, quando si chiama `tl()`, viene tracciata la stringa restituita da `makeLinkName()`. Quando  Activity Map sui collegamenti della pagina, utilizza la stessa chiamata per creare un collegamento.
3. La soluzione finale è quella di restituire il valore originale della funzione di collegamento ActivityMap predefinita. Mantenendo questo riferimento per le chiamate nel caso predefinito è possibile ignorare o scrivere solo il codice personalizzato per `makeLinkName()` e non dover fornire un valore di ritorno del collegamento per tutti i collegamenti della pagina.
