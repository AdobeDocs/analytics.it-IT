---
description: Potete utilizzare il metodo s.tl() per tenere traccia degli elementi personalizzati e per configurare il rendering delle sovrapposizioni per il contenuto dinamico.
title: Utilizzare il metodo s.tl()
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Use the `tl()` method

Potete usare il `tl()` metodo per tenere traccia degli elementi personalizzati e configurare il rendering delle sovrapposizioni per il contenuto dinamico.

## Tracciamento di elementi personalizzati {#section_5D6688DFFFC241718249A9A0C632E465}

L&#39;utilizzo del [`tl()` metodo](/help/implement/vars/functions/tl-method.md) come parte del modulo Activity Map AppMeasurement consente di tenere traccia di qualsiasi oggetto su cui si fa clic, anche degli oggetti che non sono tag di ancoraggio o elementi immagine. Con s.tl potete tenere traccia di qualsiasi elemento personalizzato che non si traduca in un caricamento di pagina.

Nel `tl()` metodo, il `linkName` parametro attualmente utilizzato per identificare i collegamenti di uscita, i collegamenti personalizzati, ecc. viene ora utilizzato anche per identificare l’ID collegamento per la variabile Activity Map.

```js
s.tl(this,linkType,linkName,variableOverrides)
```

In altre parole, se utilizzate `s.tl()` per tenere traccia degli elementi personalizzati, l&#39;ID collegamento viene estratto dal valore passato come terzo parametro (linkName) nel `s.tl()` metodo. Non viene estratto dall’algoritmo standard di tracciamento dei collegamenti utilizzato per il tracciamento [](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) predefinito nella Activity Map.

## Rendering delle sovrapposizioni per il contenuto dinamico {#section_FD24B61A732149C7B58BA957DD84A5E7}

Quando la funzione s.tl() viene chiamata direttamente dall&#39;evento on-click dell&#39;elemento HTML, Activity Map può visualizzare una sovrapposizione per tale elemento quando la pagina Web viene caricata. Esempio:

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

Ogni volta che un contenuto di una pagina Web viene aggiunto alla pagina dopo il caricamento iniziale della pagina, il `tl()` metodo viene chiamato indirettamente e non è possibile visualizzare sovrapposizioni per quel nuovo contenuto a meno che non venga espressamente attivato o fatto clic su di esso. Quindi viene attivato un nuovo processo di raccolta dei collegamenti dalla Activity Map.

Quando il `tl()` metodo non viene chiamato direttamente dall&#39;evento on-click dell&#39;elemento HTML, Activity Map può visualizzare la sovrapposizione solo dopo che l&#39;utente ha fatto clic su tale elemento. Di seguito è riportato un esempio in cui il `tl()` metodo viene chiamato indirettamente:

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Il modo migliore per Mappa dell&#39;attività per sovrapporre i collegamenti ai contenuti dinamici consiste nell&#39;impostare una funzione ActivityMap.link personalizzata per chiamare la stessa funzione il cui valore restituito viene passato a `s.tl`. Ad esempio:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

In questo caso, abbiamo ignorato la funzione ActivityMap.link per eseguire una delle tre operazioni richiamate:

1. Se linkName viene passato, questo viene chiamato da s.tl(), quindi è sufficiente restituire ciò che s.tl ha passato come linkName.
2. Questo viene chiamato da Activity Map al momento del reporting, quindi linkName non viene mai trasmesso, e quindi chiamare makeLinkName() con l&#39;elemento link. Questo è il passaggio cruciale: la chiamata &quot;makeLinkName(element)&quot; deve essere la stessa nel terzo argomento della chiamata s.tl nel `<button>` tag. Ciò significa che, quando si chiama s.tl, viene tracciata la stringa restituita da makeLinkName. Quando Mappa dell&#39;attività crea rapporti sui collegamenti nella pagina, utilizza la stessa chiamata per creare un collegamento.
3. La soluzione finale è quella di restituire il valore originale della funzione di collegamento ActivityMap predefinita. Mantenendo questo riferimento per la chiamata nel caso predefinito è possibile ignorare o scrivere solo il codice personalizzato per makeLinkName e non dover fornire un valore di ritorno del collegamento per tutti i collegamenti della pagina.
