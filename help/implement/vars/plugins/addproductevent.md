---
title: addProductEvent
description: Aggiunge eventi personalizzati alla variabile "products and events".
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in Adobe:addProductEvent

> [!IMPORTANT] Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `addProductEvent` plug-in aggiunge un evento numerico o valutario alla `products` variabile. Adobe consiglia di utilizzare questo plug-in se si desidera aggiungere un evento numerico o valutario alla `products` variabile senza preoccuparsi del formato stringa prodotto. Questo plug-in non è necessario se nella `products` variabile non vengono utilizzati eventi numerici o valutari.

## Installare il plug-in utilizzando l&#39;estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: None
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Initialize addProductEvent
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche all&#39;estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata l&#39;istanza dell&#39;oggetto di tracciamento di Analytics (tramite `s_gi`). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `addProductEvent` metodo utilizza i seguenti argomenti:

* **`en`**(obbligatorio, stringa): L’evento da aggiungere all’ultima voce della`products`variabile. Se la`products`variabile è vuota, viene creata una voce di prodotto &quot;vuota&quot; a cui è associato l&#39;evento (e il relativo valore).
* **`ev`**(obbligatorio, stringa): Il valore assegnato all&#39;evento numerico o valutario nell&#39;`en`argomento.  Il valore predefinito è`1`se non è impostato.
* **`ap`**(facoltativo, booleano): Se la variabile products contiene attualmente più di una voce di prodotto, il valore`true`(o`1`) aggiunge l’evento a tutte le voci di prodotto.  Il valore predefinito è`false`se non è impostato.

Non `addProductEvent` restituisce nulla. ma aggiunge l&#39;evento e il relativo valore alla `products` variabile. Il plug-in aggiunge automaticamente anche l’evento alla `events` variabile, in quanto è necessario anche in questo caso.

## Cookie

Il plug-in addProductEvent non crea né utilizza cookie

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase"
```

...e viene eseguito il codice seguente...

```js
s.addProductEvent("event35", "25");
```

... il valore finale di s.products sarà:

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25;event35=25"
```

...e il valore finale di s.events sarà:

```js
s.events="purchase,event35"
```

### Esempio n. 2

Se viene mostrato...

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
```

...e viene eseguito il codice seguente...

```js
s.addProductEvent("event35", 25, 1);
```

... il valore finale di s.products sarà:

```js
s.products=";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"
```

Quando il terzo argomento è uguale a true (o 1), per ogni voce di prodotto viene aggiunto al valore l’evento specificato nella chiamata

### Esempio n. 3

Se viene mostrato...

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```

...e viene eseguito il codice seguente...

```js
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

... il valore finale di s.products sarà...

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
```

...e s.events verranno impostati come segue:

```js
s.events="purchase,event2,event33,event34,event35"
```

### Esempio n. 4

Se viene mostrato...

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```

...e viene eseguito il codice seguente...

```js
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1); //The second argument can be an integer or a string representing an integer/number
s.addProductEvent("event35", "15", 1);
```

... il valore finale di s.products sarà...

```js
s.products=";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"
```

...e s.events verranno impostati come segue:

```js
s.events="purchase,event2,event33,event34,event35"
```

### Esempio n. 5

Se s.products non è impostato ed è in esecuzione il codice seguente...

```js
s.addProductEvent("event35", "25");
```

... il valore finale di s.products sarà:

```js
s.products=";;;;event35=25"
```

In questo caso, event35 verrà aggiunto anche alla fine di s.events

## Cronologia versioni

### 1.0 (7 ottobre 2019)

* Versione iniziale.
