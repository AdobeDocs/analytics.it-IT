---
description: Potete utilizzare la funzione s. tl () per tenere traccia degli elementi personalizzati e configurare il rendering delle sovrapposizioni per il contenuto dinamico.
seo-description: Potete utilizzare la funzione s. tl () per tenere traccia degli elementi personalizzati e configurare il rendering delle sovrapposizioni per il contenuto dinamico.
seo-title: Utilizzare la funzione s. tl ()
solution: Analytics
title: Utilizzare la funzione s. tl ()
topic: Activity map
uuid: 59 e 062 af -6 a 1 c -46 ff -9 c 3 b -6 cf 7 a 0453711
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilizzare la funzione s. tl ()

Potete utilizzare la funzione s. tl () per tenere traccia degli elementi personalizzati e configurare il rendering delle sovrapposizioni per il contenuto dinamico.

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

Using the [s.tl() function](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html) as part of the Activity Map AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. Utilizzando s. tl potete tenere traccia degli elementi personalizzati che non generano un caricamento di pagina.

Nella funzione s. tl, il parametro linkname attualmente utilizzato per identificare i collegamenti exit, custom links, ecc. viene ora utilizzato anche per identificare l'ID collegamento per la variabile Activity Map.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

In altre parole, se utilizzate s. tl per tenere traccia degli elementi personalizzati, l'ID del collegamento viene prelevato dal valore passato come terzo parametro (linkname) nella funzione s. tl. It is not pulled from the standard link tracking algorithm that is used for [default tracking](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) in Activity Map.

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

Quando la funzione s. tl () viene chiamata direttamente dall'evento on-clic dell'elemento HTML, la mappa dell'attività può visualizzare una sovrapposizione per quell'elemento quando la pagina Web viene caricata. Esempio:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

Ogni volta che un contenuto di una pagina Web viene aggiunto alla pagina dopo il caricamento iniziale della pagina, la funzione s. tl viene chiamata indirettamente e non possiamo visualizzare sovrapposizioni per quel nuovo contenuto a meno che non sia espressamente attivata o su cui sia stato fatto clic. Quindi, viene attivato un nuovo processo di raccolta dei collegamenti dalla Activity Map.

Quando la funzione s. tl () non viene chiamata direttamente dall'evento on-clic dell'elemento HTML, la mappa dell'attività può visualizzare la sovrapposizione solo una volta che l'utente fa clic su tale elemento. Di seguito è riportato un esempio in cui la funzione s. tl () viene chiamata indirettamente:

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

Il modo migliore per la mappa dell'attività per sovrapporre i collegamenti di contenuto dinamici consiste nel presentare una funzione activitymap. link personalizzata per chiamare la stessa funzione il cui valore restituito viene passato a s. tl. Esempio:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

Qui, abbiamo modificato la funzione activitymap. link per eseguire una delle tre operazioni quando viene chiamato:

1. Se viene passato linkname, questo viene chiamato da s. tl (), quindi restituisce semplicemente l'elemento s. tl trasmesso come linkname.
1. Questo viene chiamato dalla mappa dell'attività in fase di reporting, pertanto un linkname non viene mai passato e quindi chiama makelinkname () con l'elemento collegamento. This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. Ciò significa che quando viene chiamato s. tl, viene tracciata la stringa restituita da makelinkname. Quando i rapporti Activity Map (Mappa dell'attività) sui collegamenti della pagina vengono utilizzati per creare un collegamento,
1. La soluzione finale consiste nell'restituire il valore restituito originale della funzione di collegamento activitymap predefinita. Se si tiene presente questo riferimento per la chiamata nel caso predefinito, è possibile sostituire o scrivere codice personalizzato per makelinkname e non deve essere visualizzato un valore di ritorno per tutti i collegamenti sulla pagina.
