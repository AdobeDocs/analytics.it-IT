---
title: getValOnce
description: Impedisci che una variabile di Analytics venga impostata sullo stesso valore due volte di fila.
translation-type: tm+mt
source-git-commit: 5a81754ca6137d7bc1e790fe537acbb4bbdb8efb
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 1%

---


# Plug-in di Adobe: getValOnce

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getValOnce` impedisce che una variabile venga impostata più di una volta sullo stesso valore. Adobe consiglia di utilizzare questo plug-in quando si desidera deduplicare le occorrenze in cui un visitatore aggiorna una pagina o in altro modo visita una pagina specifica più volte. Questo plug-in non è necessario se non sei preoccupato della metrica &quot;Occorrenze&quot; in Analysis Workspace.

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
   * Tipo azione: Inizializza getValOnce
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
/* Adobe Consulting Plugin: getValOnce v3.0 (Requires AppMeasurement) */
function getValOnce(vtc,cn,et,ep){var e=vtc,k=cn,l=et,m=ep;if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,a;b<window.s_c_il.length;b++)if(a=window.s_c_il[b],a._c&&"s_c"===a._c)return a}();"undefined"!==typeof c&&(c.contextData.getValOnce="3.0");window.cookieWrite=window.cookieWrite||function(b,a,d){if("string"===typeof b){var h=window.location.hostname,c=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){c=2<c?
c:2;var f=h.lastIndexOf(".");if(0<=f){for(;0<=f&&1<c;)f=h.lastIndexOf(".",f-1),c--;f=0<f?h.substring(f):h}}g=f;a="undefined"!==typeof a?""+a:"";if(d||""===a)if(""===a&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return b&&(document.cookie=encodeURIComponent(b)+"="+encodeURIComponent(a)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(b)===a:!1}};window.cookieRead=window.cookieRead||function(b){if("string"===
typeof b)b=encodeURIComponent(b);else return"";var a=" "+document.cookie,d=a.indexOf(" "+b+"="),c=0>d?d:a.indexOf(";",d);return(b=0>d?"":decodeURIComponent(a.substring(d+2+b.length,0>c?a.length:c)))?b:""};return e&&(k=k||"s_gvo",l=l||0,m="m"===m?6E4:864E5,e!==this.c_r(k))?(c=new Date,c.setTime(c.getTime()+l*m),cookieWrite(k,e,0===l?0:m),e):""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getValOnce` utilizza i seguenti argomenti:

* **`vtc`** (obbligatorio, stringa): Variabile da controllare e vedere se è stata impostata in precedenza su un valore identico
* **`cn`** (facoltativo, stringa): Nome del cookie che contiene il valore da controllare. Valori predefiniti in `"s_gvo"`
* **`et`** (facoltativo, numero intero): La scadenza del cookie in giorni (o minuti, a seconda dell’ `ep` argomento). Predefinito su `0`, che scade alla fine della sessione del browser
* **`ep`** (facoltativo, stringa): Imposta questo argomento solo se è impostato anche l&#39; `et` argomento. Imposta questo argomento su `"m"` se desideri che l&#39;argomento `et` scada in minuti invece che in giorni. Il valore predefinito è `"d"`, che imposta l&#39;argomento `et` in giorni.

Se l&#39;argomento `vtc` e il valore del cookie corrispondono, questo metodo restituisce una stringa vuota. Se l&#39;argomento `vtc` e il valore del cookie non corrispondono, il metodo restituisce l&#39;argomento `vtc` come stringa.

## Chiamate di esempio

### Esempio n. 1

Usa questa chiamata per evitare che lo stesso valore venga passato a s.campaign più di una volta alla riga per i successivi 30 giorni:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

Nella chiamata precedente, il plug-in confronterà prima il valore già contenuto nel cookie s_campaign con il valore proveniente dalla variabile s.campaign corrente.   Se non viene effettuata una corrispondenza, il plug-in imposta il cookie s_campaign su uguale al nuovo valore proveniente da s.campaign e restituisce il nuovo valore.   Questo confronto avverrà nei prossimi trenta giorni

### Esempio n. 3

Usa questa chiamata per evitare che lo stesso valore venga impostato durante l&#39;intera sessione:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Questo codice impedisce che lo stesso valore venga passato in s.eVar2 più di una volta alla riga durante l&#39;intera sessione dell&#39;utente.  Ignora anche il valore &quot;m&quot; nel parametro (alla fine della chiamata) poiché il tempo di scadenza è impostato su 0.   Il codice memorizza anche il valore di confronto nel cookie s_ev2.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2,01

* È stato risolto un problema relativo alla scrittura di cookie.

### 2.0

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).

### 1.1.

* È stata aggiunta l’opzione per scegliere minuti o giorni per la scadenza tramite il parametro `t` .
* Correzione dell&#39;ambito della variabile `k` utilizzata per limitarla solo al plug-in. Questa modifica impedisce possibili interferenze con altro codice sulla pagina.
