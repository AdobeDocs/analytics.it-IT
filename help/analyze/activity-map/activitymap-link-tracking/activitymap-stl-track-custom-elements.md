---
description: Potete utilizzare la funzione s.tl() per tenere traccia degli elementi personalizzati e per configurare il rendering delle sovrapposizioni per il contenuto dinamico.
seo-description: Potete utilizzare la funzione s.tl() per tenere traccia degli elementi personalizzati e per configurare il rendering delle sovrapposizioni per il contenuto dinamico.
seo-title: Utilizzare la funzione s.tl()
solution: Analytics
title: Utilizzare la funzione s.tl()
topic: Activity Map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Utilizzare la funzione s.tl()

Potete utilizzare la funzione s.tl() per tenere traccia degli elementi personalizzati e per configurare il rendering delle sovrapposizioni per il contenuto dinamico.

## Tracciamento di elementi personalizzati {#section_5D6688DFFFC241718249A9A0C632E465}

L'utilizzo della funzione [s.tl()](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html) come parte del modulo Activity Map AppMeasurement consente di tenere traccia di qualsiasi oggetto su cui si fa clic, anche degli oggetti che non sono tag di ancoraggio o elementi immagine. Con s.tl potete tenere traccia di qualsiasi elemento personalizzato che non si traduca in un caricamento di pagina.

Nella funzione s.tl, il parametro linkName attualmente utilizzato per identificare i collegamenti di uscita, i collegamenti personalizzati, ecc. viene ora utilizzato anche per identificare l’ID collegamento per la variabile Activity Map.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

In altre parole, se utilizzate s.tl per tracciare gli elementi personalizzati, l'ID collegamento viene estratto dal valore passato come terzo parametro (linkName) nella funzione s.tl. Non viene estratto dall’algoritmo standard di tracciamento dei collegamenti utilizzato per il tracciamento [](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) predefinito nella Activity Map.

## Rendering delle sovrapposizioni per il contenuto dinamico {#section_FD24B61A732149C7B58BA957DD84A5E7}

Quando la funzione s.tl() viene chiamata direttamente dall'evento on-click dell'elemento HTML, Activity Map può visualizzare una sovrapposizione per tale elemento quando la pagina Web viene caricata. Esempio:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

Ogni volta che un contenuto di una pagina Web viene aggiunto alla pagina dopo il caricamento iniziale della pagina, la funzione s.tl viene richiamata indirettamente e non è possibile visualizzare sovrapposizioni per quel nuovo contenuto a meno che non sia espressamente attivato o fatto clic su di esso. Quindi viene attivato un nuovo processo di raccolta dei collegamenti dalla Activity Map.

Quando la funzione s.tl() non viene chiamata direttamente dall'evento on-click dell'elemento HTML, Activity Map può visualizzare la sovrapposizione solo dopo che l'utente ha fatto clic su di esso. Di seguito è riportato un esempio di chiamata indiretta della funzione s.tl():

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

Il modo migliore per Mappa dell'attività per sovrapporre i collegamenti ai contenuti dinamici consiste nell'impostare una funzione ActivityMap.link personalizzata per chiamare la stessa funzione il cui valore restituito viene passato a s.tl. Esempio:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

In questo caso, abbiamo ignorato la funzione ActivityMap.link per eseguire una delle tre operazioni richiamate:

1. Se linkName viene passato, questo viene chiamato da s.tl(), quindi è sufficiente restituire ciò che s.tl ha passato come linkName.
1. Questo viene chiamato da Activity Map al momento del reporting, quindi linkName non viene mai trasmesso, e quindi chiamare makeLinkName() con l'elemento link. Questo è il passaggio cruciale: la chiamata "makeLinkName(element)" deve essere la stessa nel terzo argomento della chiamata s.tl nel `<button>` tag. Ciò significa che, quando si chiama s.tl, viene tracciata la stringa restituita da makeLinkName. Quando Mappa dell'attività riporta sui collegamenti della pagina, utilizza la stessa chiamata per creare un collegamento.
1. La soluzione finale è quella di restituire il valore originale della funzione di collegamento ActivityMap predefinita. Mantenendo questo riferimento per la chiamata nel caso predefinito è possibile ignorare o scrivere solo il codice personalizzato per makeLinkName e non dover fornire un valore di ritorno del collegamento per tutti i collegamenti della pagina.
