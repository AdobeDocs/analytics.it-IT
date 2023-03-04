---
title: getNewRepeat
description: Tracciare l’attività dei visitatori nuovi rispetto a quelli ripetuti.
feature: Variables
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 4%

---

# Plug-in di Adobe: getNewRepeat

{{plug-in}}

Il `getNewRepeat` Il plug-in consente di determinare se un visitatore del sito è un nuovo visitatore o un visitatore ripetuto entro un numero desiderato di giorni. L’Adobe consiglia di utilizzare questo plug-in se desideri identificare i visitatori come &quot;nuovi&quot; utilizzando un numero di giorni personalizzato. Questo plug-in non è necessario se le dimensioni Visitatore nuovo/ripetuto in Analysis Workspace soddisfano le esigenze della tua organizzazione.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getNewRepeat
1. Save and publish the changes to the rule.-->

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione del plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi [!UICONTROL Configure tracking using custom code] Pannello a soffietto, che mostra [!UICONTROL Open Editor] pulsante.
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell’istanza dell’oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getNewRepeat` La funzione utilizza i seguenti argomenti:

* **`d`** (numero intero, facoltativo): il numero minimo di giorni necessari tra una visita e l’altra per reimpostare i visitatori su `"New"`. Se questo argomento non è impostato, il valore predefinito è 30 giorni.

Questa funzione restituisce il valore di `"New"` se il cookie impostato dal plug-in non esiste o è scaduto. Restituisce il valore di `"Repeat"` se il cookie impostato dal plug-in esiste e il tempo trascorso dall’hit corrente e dal momento impostato nel cookie è superiore a 30 minuti. Questa funzione restituisce lo stesso valore per un’intera visita.

Questo plug-in utilizza un cookie denominato `"s_nr[LENGTH]"` dove `[LENGTH]` è uguale a `d` argomento. Il cookie contiene una marca temporale Unix che rappresenta l’ora corrente e lo stato corrente del visitatore (`"New"` o `"Repeat"`).

## Esempi

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.1 (30 settembre 2019)

* Ridisposizione della logica JavaScript per ridurre le dimensioni del plug-in

### 2.0 (16 aprile 2018)

* Ricompilato con dimensioni del codice inferiori
* È stata rimossa la possibilità di denominare il cookie per memorizzare le informazioni sulla visita. Il plug-in ora assegna dinamicamente un nome al cookie in base al valore passato nel `d` argomento.
