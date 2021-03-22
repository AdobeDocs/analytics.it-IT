---
title: addProductEvent
description: Aggiunge eventi personalizzati alla variabile prodotti ed eventi .
translation-type: tm+mt
source-git-commit: 3359ed8e7ef7979be57ca5ec9ca1803fc52afe88
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 1%

---


# Plug-in di Adobe: addProductEvent

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `addProductEvent` aggiunge un evento numerico o valutario alla variabile [`products`](../page-vars/products.md) . Adobe consiglia di utilizzare questo plug-in se si desidera aggiungere un evento numerico o valutario alla variabile `products` senza preoccuparsi del formato della stringa di prodotto. Questo plug-in non è necessario se non utilizzi eventi numerici o valutari nella variabile `products` .

## Installare il plug-in utilizzando l’estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza addProductEvent
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato di Launch

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi il [!UICONTROL Configure tracking using custom code] pannello a soffietto, che mostra il pulsante [!UICONTROL Open Editor] .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `addProductEvent` utilizza i seguenti argomenti:

* **`en`** (obbligatorio, stringa): L’evento da aggiungere all’ultima voce della  `products` variabile. Se la variabile `products` è vuota, viene creata una voce di prodotto &quot;vuota&quot; con l’evento (e il relativo valore) associato.
* **`ev`** (obbligatorio, stringa): Valore assegnato all&#39;evento numerico o di valuta nell&#39; `en` argomento.  Se non è impostato, viene impostato il valore predefinito `1`.
* **`ap`** (facoltativo, booleano): Se la variabile &quot;products&quot; contiene attualmente più di una voce di prodotto, il valore  `true` (o  `1`) aggiunge l’evento a tutte le voci di prodotto.  Se non è impostato, viene impostato il valore predefinito `false`.

`addProductEvent` non restituisce nulla. Al contrario, aggiunge l&#39;evento e il relativo valore alla variabile `products` . Il plug-in aggiunge automaticamente anche l&#39;evento alla variabile [`events`](../page-vars/events/events-overview.md) , poiché è necessario anche in questo caso.

## Cookie

Il plug-in addProductEvent non crea o utilizza cookie

## Chiamate di esempio

### Esempio n. 1

Il codice seguente imposta la variabile `s.products` su `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

Il codice riportato sopra imposta anche la variabile `s.events` su `"purchase,event35"`

### Esempio n. 3

Il codice seguente imposta la variabile `s.products` su `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Quando il terzo argomento nella chiamata `addProductEvent` è `true` (o `1`), ogni voce di prodotto ha l’evento specificato nella chiamata aggiunta al suo valore.

### Esempio n. 3

Il codice seguente imposta la variabile `s.products` su `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

Il codice riportato sopra imposta anche la variabile `s.events` su `"purchase,event2,event33,event34,event35"`

### Esempio n. 4

Il codice seguente imposta la variabile `s.products` su `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

Il codice riportato sopra imposta anche la variabile `s.events` su `"purchase,event2,event33,event34,event35"`.

>[!NOTE]
>
>Il secondo argomento della chiamata può essere un numero intero **o** una stringa che rappresenta un numero intero/numerico

### Esempio n. 5

Se `s.products` non è già impostato, il codice seguente lo imposta su `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

Il codice di cui sopra aggiunge anche `"event35"` alla fine di `s.events` **o**, se `s.events` non è già impostato, il codice di cui sopra imposta `s.events` a `"event35"`

## Cronologia versioni

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (7 ottobre 2019)

* Versione iniziale.
