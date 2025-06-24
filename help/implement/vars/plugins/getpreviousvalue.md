---
title: getPreviousValue
description: Ottieni l’ultimo valore passato in una variabile.
feature: Appmeasurement Implementation
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 6%

---

# Plug-in Adobe: getPreviousValue

{{plug-in}}

Il plug-in `getPreviousValue` consente di impostare una variabile su un valore impostato su un hit precedente. Questo plug-in non è necessario se l’implementazione contiene tutti i valori desiderati nell’hit corrente.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fare clic su **[!UICONTROL Tags]** a sinistra, quindi fare clic sulla proprietà tag desiderata.
1. Fai clic su **[!UICONTROL Extensions]** a sinistra, quindi sulla scheda **[!UICONTROL Catalog]**
1. Individuare e installare l&#39;estensione **[!UICONTROL Common Web SDK Plugins]**.
1. Fai clic su **[!UICONTROL Data Elements]** a sinistra, quindi sull&#39;elemento dati desiderato.
1. Imposta il nome dell’elemento dati desiderato con la seguente configurazione:
   * Estensione: Common Web SDK Plugins
   * Elemento dati: `getPreviousValue`
1. Imposta i parametri desiderati a destra.
1. Salva e pubblica le modifiche apportate all’elemento dati.

## Installare manualmente il plug-in implementando Web SDK

Questo plug-in non è ancora supportato per l&#39;utilizzo in un&#39;implementazione manuale del Web SDK.

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
   * Tipo azione: inizializzare getPreviousValue
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

Copiare e incollare il codice seguente in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta Adobe a risolvere eventuali problemi.

```js
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `getPreviousValue` utilizza i seguenti argomenti:

* **`v`** (stringa, obbligatorio): variabile con il valore che si desidera passare alla successiva richiesta di immagine. Una variabile comune utilizzata è `s.pageName` per recuperare il valore della pagina precedente.
* **`c`** (stringa, facoltativo): nome del cookie che memorizza il valore.  Se questo argomento non è impostato, verrà utilizzato per impostazione predefinita `"s_gpv"`.

Quando chiami questa funzione, restituisce il valore stringa contenuto nel cookie. Il plug-in reimposta la scadenza del cookie e assegna il valore della variabile dall&#39;argomento `v`. Il cookie scade dopo 30 minuti di inattività.

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

Se la variabile associata all&#39;argomento `v` è impostata su un nuovo valore e il plug-in `getPreviousValue` viene eseguito MA non viene inviata contemporaneamente una chiamata al server Analytics, il nuovo valore dell&#39;argomento `v` verrà comunque considerato il &quot;valore precedente&quot; alla successiva esecuzione del plug-in.
Ad esempio, supponiamo che il seguente codice venga eseguito sulla prima pagina della visita:

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Questo codice genera una chiamata al server in cui `pageName` è &quot;Home&quot; e prop7 non è impostato.  Tuttavia, la chiamata a `getPreviousValue` memorizza il valore di `pageName` nel cookie `gpv_Page`. Supponiamo che subito dopo, sulla stessa pagina, venga eseguito il seguente codice:

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

Poiché la funzione `t()` non viene eseguita in questo blocco di codice, non viene inviata un&#39;altra richiesta di immagine.  Tuttavia, quando il codice della funzione `getPreviousValue` viene eseguito questa volta, `prop7` è impostato sul valore precedente di `pageName` (&quot;Home&quot;), quindi memorizza il nuovo valore di `pageName` (&quot;Nuovo valore&quot;) nel cookie `gpv_Page`. Quindi, supponiamo che il visitatore passi a una pagina diversa e che il seguente codice venga eseguito su questa pagina:

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Quando la funzione `t()` viene eseguita, viene creata una richiesta di immagine in cui `pageName` è &quot;Pagina 2&quot; e `prop7` è &quot;Nuovo valore&quot;, ovvero il valore di `pageName` quando è stata effettuata l&#39;ultima chiamata a `getPreviousValue`. Il valore `prop7` di `"Home"` non è mai stato contenuto in una richiesta di immagine, anche se &quot;Home&quot; è stato il primo valore passato a `pageName`.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v2.0 (7 ottobre 2019)

* Versione punto (riscrittura logica completa).
