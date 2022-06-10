---
title: getPreviousValue
description: Ottieni l’ultimo valore trasmesso in una variabile.
feature: Variables
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Plug-in di Adobe: getPreviousValue

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `getPreviousValue` il plug-in consente di impostare una variabile su un valore impostato su un hit precedente. Questo plug-in non è necessario se l&#39;implementazione contiene tutti i valori desiderati nell&#39;hit corrente.

## Installare il plug-in utilizzando l’SDK per web o l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getPreviousValue
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getPreviousValue` La funzione utilizza i seguenti argomenti:

* **`v`** (stringa, obbligatoria): Variabile con il valore che si desidera passare alla richiesta di immagine successiva. Una variabile comune utilizzata è `s.pageName` per recuperare il valore della pagina precedente.
* **`c`** (stringa, facoltativo): Nome del cookie che memorizza il valore.  Se questo argomento non è impostato, viene utilizzata l&#39;impostazione predefinita `"s_gpv"`.

Quando si chiama questa funzione, restituisce il valore stringa contenuto nel cookie. Il plug-in quindi reimposta la scadenza del cookie e gli assegna il valore della variabile dal `v` argomento. Il cookie scade dopo 30 minuti di inattività.

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

## Soste improbabili

Se la variabile associata alla variabile `v` viene impostato su un nuovo valore e `getPreviousValue` il plug-in viene eseguito MA NON viene inviata contemporaneamente una chiamata al server di Analytics, il nuovo `v` il valore dell’argomento viene comunque considerato come &quot;valore precedente&quot; alla successiva esecuzione del plug-in.
Ad esempio, si supponga che il seguente codice venga eseguito sulla prima pagina della visita:

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Questo codice genera una chiamata al server in cui `pageName` è &quot;Home&quot; e prop7 non è impostato.  Tuttavia, la chiamata a `getPreviousValue` memorizza il valore di `pageName` in `gpv_Page` cookie. Si supponga che subito dopo, sulla stessa pagina, venga eseguito il seguente codice:

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

Dal momento che `t()` non viene eseguita in questo blocco di codice, non viene inviata un&#39;altra richiesta di immagine.  Tuttavia, quando `getPreviousValue` il codice della funzione viene eseguito questa volta, `prop7` è impostato sul valore precedente di `pageName` (&quot;Home&quot;), quindi memorizza il nuovo valore di `pageName` (&quot;Nuovo valore&quot;) nel `gpv_Page` cookie. Quindi, si supponga che il visitatore passi a una pagina diversa ed esegua il seguente codice su questa pagina:

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Quando il `t()` viene eseguita, viene creata una richiesta di immagine in cui `pageName` è &quot;Pagina 2&quot; e `prop7` è &quot;Nuovo valore&quot;, che era il valore di `pageName` quando l’ultima chiamata a `getPreviousValue` ebbe luogo. La `prop7` valore `"Home"` non è mai stato contenuto in una richiesta di immagine, anche se &quot;Home&quot; è stato il primo valore trasmesso a `pageName`.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v2.0 (7 ottobre 2019)

* Rilascio del punto (riscrittura logica completa).
