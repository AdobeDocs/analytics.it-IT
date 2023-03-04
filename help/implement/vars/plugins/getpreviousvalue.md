---
title: getPreviousValue
description: Ottieni l’ultimo valore passato in una variabile.
feature: Variables
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Plug-in di Adobe: getPreviousValue

{{plug-in}}

Il `getPreviousValue` Il plug-in consente di impostare una variabile su un valore impostato su un hit precedente. Questo plug-in non è necessario se l’implementazione contiene tutti i valori desiderati nell’hit corrente.

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
    * Action Type: Initialize getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getPreviousValue` La funzione utilizza i seguenti argomenti:

* **`v`** (stringa, obbligatorio): variabile con il valore che desideri trasmettere alla successiva richiesta di immagine. Una variabile comune utilizzata è `s.pageName` per recuperare il valore della pagina precedente.
* **`c`** (stringa, facoltativo): nome del cookie che memorizza il valore.  Se questo argomento non è impostato, viene utilizzato il valore predefinito `"s_gpv"`.

Quando chiami questa funzione, restituisce il valore stringa contenuto nel cookie. Il plug-in reimposta la scadenza del cookie e gli assegna il valore di variabile dalla `v` argomento. Il cookie scade dopo 30 minuti di inattività.

## Esempi

```js
// 1. Sets prop7 to the cookie value contained in gpv_Page
// 2. Resets the gpv_Page cookie value to the page variable
// 3. If the page variable is not set, reset the gpv_Page cookie expiration
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if event1 is in the events variable.
if(inList(s.events,"event1")) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if the page variable is currently set on the page
if(s.pageName) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets eVar10 equal to the cookie value contained in s_gpv, then sets the s_gpv cookie to the current value of eVar1.
s.eVar10 = getPreviousValue(s.eVar1);
```

## Quirks improbabili

Se la variabile associata alla `v` è impostato su un nuovo valore e il `getPreviousValue` viene eseguito MA una chiamata al server Analytics NON viene inviata contemporaneamente, il nuovo `v` Il valore dell&#39;argomento viene comunque considerato il &quot;valore precedente&quot; alla successiva esecuzione del plug-in.
Ad esempio, supponiamo che il seguente codice venga eseguito sulla prima pagina della visita:

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Questo codice genera una chiamata al server in cui `pageName` è &quot;Home&quot; e prop7 non è impostato.  Tuttavia, l’invito a `getPreviousValue` memorizza il valore di `pageName` nel `gpv_Page` cookie. Supponiamo che subito dopo, sulla stessa pagina, venga eseguito il seguente codice:

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

Poiché il `t()` funzione non viene eseguita in questo blocco di codice, un’altra richiesta di immagine non viene inviata.  Tuttavia, quando `getPreviousValue` il codice di funzione viene eseguito in questo momento, `prop7` è impostato sul valore precedente di `pageName` (&quot;Home&quot;), quindi memorizza il nuovo valore di `pageName` (&quot;Nuovo valore&quot;) nella `gpv_Page` cookie. Quindi, supponiamo che il visitatore passi a una pagina diversa e che il seguente codice venga eseguito su questa pagina:

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Quando `t()` viene eseguita, crea una richiesta di immagine in cui `pageName` è &quot;Page 2&quot; e `prop7` è &quot;New value&quot;, che era il valore di `pageName` quando l’ultima chiamata a `getPreviousValue` ha avuto luogo. Il `prop7` valore di `"Home"` non è mai stato contenuto in una richiesta di immagine, anche se &quot;Home&quot; è stato il primo valore passato a `pageName`.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v2.0 (7 ottobre 2019)

* Versione punto (riscrittura logica completa).
