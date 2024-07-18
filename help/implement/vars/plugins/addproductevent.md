---
title: addProductEvent
description: Aggiunge eventi personalizzati alla variabile prodotti ed eventi.
feature: Variables
exl-id: 74f4cb93-714a-4d2b-88f3-408d032f6811
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 7%

---

# Plug-in di Adobe: addProductEvent

{{plug-in}}

Il plug-in `addProductEvent` aggiunge un evento numerico o di valuta alla variabile [`products`](../page-vars/products.md). L&#39;Adobe consiglia di utilizzare questo plug-in se si desidera aggiungere un evento numerico o di valuta alla variabile `products` senza preoccuparsi del formato della stringa di prodotto. Questo plug-in non è necessario se non si utilizzano eventi numerici o di valuta nella variabile `products`.

## Installare il plug-in utilizzando l’estensione Web SDK o Web SDK

Questo plug-in non è ancora supportato per l’utilizzo nell’SDK per web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Initialize Plug-ins&quot; (Inizializza plug-in) con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Library Loaded (Page Top)
1. Aggiungi un’azione alla regola precedente con la seguente configurazione:
   * Estensione: Common Analytics Plugins
   * Tipo azione: inizializza addProductEvent
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Configure tracking using custom code], che mostra il pulsante [!UICONTROL Open Editor].
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiare e incollare il codice seguente in qualsiasi punto del file di AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `addProductEvent` utilizza i seguenti argomenti:

* **`en`** (obbligatorio, stringa): evento da aggiungere all&#39;ultima voce della variabile `products`. Se la variabile `products` è vuota, viene creata una voce di prodotto &quot;vuota&quot; con l&#39;evento (e il relativo valore) associato.
* **`ev`** (obbligatorio, stringa): valore assegnato all&#39;evento numerico o di valuta nell&#39;argomento `en`.  Impostazione predefinita: `1` se non impostata. Sono validi anche i numeri non racchiusi tra virgolette.
* **`ap`** (facoltativo, booleano): se la variabile dei prodotti contiene attualmente più di una voce di prodotto, un valore di `true` (o `1`) aggiunge l&#39;evento a tutte le voci di prodotto.  Impostazione predefinita: `false` se non impostata.

`addProductEvent` non restituisce nulla. Aggiunge invece l&#39;evento e il relativo valore alla variabile `products`. Il plug-in aggiunge inoltre automaticamente l&#39;evento alla variabile [`events`](../page-vars/events/events-overview.md), in quanto è obbligatorio in tale variabile.

## Cookie

La funzione `addProductEvent` non crea né utilizza cookie.

## Esempi

```js
// Sets the products variable to ";product1;3;300,;product2;2;122,;product3;1;25;event35=25".
// Also sets the events variable to "purchase,event35".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
s.events = "purchase";
addProductEvent("event35", "25");

// Sets the products variable to ";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvent("event35", 25, true);

// Sets the products variable to ";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
// Also sets the s.events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
addProductEvent("event33", "12");
addProductEvent("event34", "10");
addProductEvent("event35", "15");

// Sets the products variable to ";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15".
// Also sets the events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
addProductEvent("event33", "12", 1);
addProductEvent("event34", 10, 1);
addProductEvent("event35", "15", 1);

// If the products variable isn't already set, sets it to ";;;;event35=25".
// Also appends event35 to the events variable.
addProductEvent("event35", "25");
```

## Cronologia versioni

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (7 ottobre 2019)

* Versione iniziale.
