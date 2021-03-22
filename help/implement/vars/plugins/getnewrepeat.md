---
title: getNewRepeat
description: Tracciare l’attività dei visitatori nuovi rispetto a quelli ripetuti.
translation-type: tm+mt
source-git-commit: 9d44226202cd690d069f9c0c85c8af2ef8fd0106
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 0%

---


# Plug-in di Adobe: getNewRepeat

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getNewRepeat` consente di determinare se un visitatore del sito è un nuovo visitatore o un visitatore ripetuto entro un numero desiderato di giorni. Adobe consiglia di utilizzare questo plug-in se desideri identificare i visitatori come &quot;nuovi&quot; utilizzando un numero personalizzato di giorni. Questo plug-in non è necessario se le dimensioni Nuovo/Ripeti visitatore in Analysis Workspace soddisfano le esigenze della tua organizzazione.

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
   * Tipo azione: Inizializza getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getNewRepeat` utilizza i seguenti argomenti:

* **`d`** (intero, facoltativo): Il numero minimo di giorni necessari tra le visite che reimposta i visitatori su  `"New"`. Se questo argomento non viene impostato, viene impostato automaticamente su 30 giorni.

Questo metodo restituisce il valore di `"New"` se il cookie impostato dal plug-in non esiste o è scaduto. Restituisce il valore di `"Repeat"` se il cookie impostato dal plug-in esiste e il tempo trascorso dall&#39;hit corrente e il tempo impostato nel cookie è maggiore di 30 minuti. Questo metodo restituisce lo stesso valore per un’intera visita.

Questo plug-in utilizza un cookie denominato `"s_nr[LENGTH]"` in cui `[LENGTH]` è uguale all&#39;argomento `d`. Il cookie contiene una marca temporale Unix che rappresenta l&#39;ora corrente e lo stato corrente del visitatore (`"New"` o `"Repeat"`).

## Chiamate di esempio

### Esempio n. 1

Il codice seguente imposterà s.eVar1 uguale al valore di &quot;Nuovo&quot; per i nuovi visitatori e continuerà a impostare s.eVar1 uguale al valore di &quot;Nuovo&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore al sito.

```js
s.eVar1=s.getNewRepeat();
```

### Esempio n. 2

Se il visitatore ritorna al sito in qualsiasi momento da 31 minuti a 30 giorni dall&#39;ultima chiamata a s.getNewRepeat(), il codice seguente imposta s.eVar1 uguale al valore di &quot;Repeat&quot; e continuerà a impostare s.eVar1 uguale al valore di &quot;Repeat&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore al sito.

```js
s.eVar1=s.getNewRepeat();
```

### Esempio n. 3

Se il visitatore non è stato sul sito per almeno 30 giorni dall&#39;ultima chiamata a s.getNewRepeat(), il codice seguente imposterà s.eVar1 uguale al valore di &quot;New&quot; e continuerà a impostare s.eVar1 uguale al valore di &quot;New&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore al sito.

```js
s.eVar1=s.getNewRepeat();
```

### Esempio n. 4

Se il visitatore ritorna al sito in qualsiasi momento 31 minuti a 365 giorni (cioè 1 anno) dall&#39;ultima chiamata a s.getNewRepeat(), il seguente codice imposta s.eVar1 uguale al valore di &quot;Repeat&quot; e continuerà a impostare s.eVar1 uguale al valore di &quot;Repeat&quot; (con ogni nuova chiamata) per tutto il resto del visitatore. Visita al sito.

```js
s.eVar1=s.getNewRepeat(365);
```

### Esempio n. 5

Se il visitatore non è stato sul sito per almeno 365 giorni (cioè 1 anno) dall&#39;ultima chiamata a s.getNewRepeat(), il seguente codice imposterà s.eVar1 uguale al valore di &quot;Nuovo&quot; e continuerà a impostare s.eVar1 uguale al valore di &quot;Nuovo&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore. al sito.

```js
s.eVar1=s.getNewRepeat(365);
```

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.1 (30 settembre 2019)

* Riorganizzazione della logica JavaScript per ridurre le dimensioni del plug-in

### 2.0 (16 aprile 2018)

* Ricompilato con dimensioni di codice più piccole
* È stata rimossa la possibilità di denominare il cookie per memorizzare le informazioni sulla visita. Il plug-in ora assegna un nome dinamico al cookie in base al valore passato nell&#39;argomento `d` .
