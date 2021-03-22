---
title: getPreviousValue
description: Ottieni l’ultimo valore trasmesso in una variabile.
translation-type: tm+mt
source-git-commit: a58e57438fdbac6f2e84c5f85388dff3a43dbd3b
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 0%

---


# Plug-in di Adobe: getPreviousValue

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getPreviousValue` consente di impostare una variabile su un valore impostato su un hit precedente. Questo plug-in non è necessario se l&#39;implementazione contiene tutti i valori desiderati nell&#39;hit corrente.

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
   * Tipo azione: Inizializza getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getPreviousValue` utilizza i seguenti argomenti:

* **`v`** (stringa, obbligatoria): Variabile con il valore che si desidera passare alla richiesta di immagine successiva. Una variabile comune utilizzata è `s.pageName` per recuperare il valore della pagina precedente.
* **`c`** (stringa, facoltativo): Nome del cookie che memorizza il valore.  Se questo argomento non è impostato, viene impostato automaticamente su `"s_gpv"`.

Quando si chiama questo metodo, restituisce il valore stringa contenuto nel cookie. Il plug-in quindi reimposta la scadenza del cookie e gli assegna il valore della variabile dall&#39;argomento `v` . Il cookie scade dopo 30 minuti di inattività.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Imposta s.prop7 come valore passato in s.pageName nella richiesta di immagine precedente (ovvero il valore memorizzato nel cookie &quot;gpv_Page&quot;)
* Il codice reimposta il cookie &quot;gpv_Page&quot;, facendolo corrispondere al valore corrente di s.pageName
* Se s.pageName non è impostato al momento dell&#39;esecuzione di questo codice, allora il codice reimposterà la scadenza per il valore corrente del cookie

### Esempio n. 3

Il codice seguente imposta s.prop7 come ultimo valore passato in s.pageName, ma solo se event1 è incluso anche all&#39;interno di s.events, come determinato dal plug-in inList, al momento in cui avviene la chiamata.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Esempio n. 3

Il codice seguente imposta s.prop7 come ultimo valore passato in s.pageName ma solo se s.pageName è attualmente impostato sulla pagina nello stesso momento.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Esempio n. 4

Il codice seguente imposta s.eVar10 come valore passato in s.eVar1 nella richiesta di immagine precedente.   Il precedente valore eVar1 sarebbe stato contenuto nel cookie &quot;s_gpv&quot;.  Il codice imposta quindi il cookie &quot;s_gpv&quot; uguale al valore corrente di s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Soste improbabili

Se la variabile associata all&#39;argomento v è impostata su un nuovo valore e il plug-in getPreviousValue viene eseguito MA una chiamata al server Analytics NON viene inviata contemporaneamente, il nuovo valore dell&#39;argomento v sarà comunque considerato il &quot;valore precedente&quot; al successivo avvio del plug-in.
Ad esempio, si supponga che il seguente codice venga eseguito sulla prima pagina della visita:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Questo codice produrrebbe una chiamata al server in cui l&#39;argomento pageName è uguale a &quot;home&quot; e l&#39;argomento p7 (prop7) non è impostato.  Tuttavia, la chiamata a s.getPreviousValue memorizzerebbe il valore di s.pageName (ovvero &quot;home&quot;) nel cookie specificato nella chiamata (ovvero il cookie &quot;gpv_Page&quot;).
Ora, si supponga che subito dopo, sulla stessa pagina, venga eseguito il seguente codice (per qualsiasi motivo):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Poiché la funzione s.t() non viene eseguita in questo blocco di codice, non verrà creata un’altra richiesta di immagine.  Tuttavia, quando il codice della funzione s.getPreviousValue() viene eseguito questa volta, s.prop7 verrà impostato su uguale al valore precedente di s.pageName (cioè &quot;home&quot;) e quindi memorizzerà il nuovo valore di s.pageName (ovvero &quot;happy value&quot;) nel cookie &quot;gpv_Page&quot;.
Supponiamo che il visitatore passi a una pagina diversa e che il seguente codice venga eseguito su questa pagina:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Quando la funzione di chiamata s.t() viene eseguita, crea una richiesta di immagine in cui s.pageName=&quot;page 2&quot; e s.prop7 è uguale a &quot;valore felice&quot;, che era il valore di s.pageName quando è avvenuta l’ultima chiamata a getPreviousValue.   Il valore s.prop7 di &quot;home&quot; non è mai stato contenuto in alcuna richiesta di immagine reale, anche se &quot;home&quot; è stato il primo valore passato in s.pageName.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v2.0 (7 ottobre 2019)

* Rilascio del punto (riscrittura logica completa).
