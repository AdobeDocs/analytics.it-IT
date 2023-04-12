---
title: getValOnce
description: Impedisci che una variabile di Analytics venga impostata sullo stesso valore due volte di fila.
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 9%

---

# Plug-in di Adobe: getValOnce

{{plug-in}}

La `getValOnce` il plug-in impedisce che una variabile venga impostata più di una volta sullo stesso valore. Adobe consiglia di utilizzare questo plug-in quando si desidera deduplicare le occorrenze in cui un visitatore aggiorna una pagina o in altro modo visita una pagina specifica più volte. Questo plug-in non è necessario se non sei preoccupato della metrica &quot;Occorrenze&quot; in Analysis Workspace.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con l’SDK per web.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic su **[!UICONTROL Tags]** a sinistra, quindi fai clic sulla proprietà tag desiderata.
1. Fai clic su **[!UICONTROL Extensions]** a sinistra, quindi fai clic sul pulsante **[!UICONTROL Catalog]** scheda
1. Individua e installa il **[!UICONTROL Common Web SDK Plugins]** estensione.
1. Fai clic su **[!UICONTROL Data Elements]** a sinistra, quindi fai clic sull’elemento dati desiderato.
1. Imposta il nome dell&#39;elemento dati desiderato con la seguente configurazione:
   * Estensione: Plug-in SDK per web comuni
   * Elemento dati: `getValOnce`
1. Imposta i parametri desiderati a destra.
1. Salva e pubblica le modifiche apportate all’elemento dati.

## Installare il plug-in manualmente durante l’implementazione dell’SDK per web

Questo plug-in non è ancora supportato per l&#39;utilizzo in un&#39;implementazione manuale dell&#39;SDK web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getValOnce
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v3.1 */
function getValOnce(vtc,cn,et,ep){var e=vtc,i=cn,t=et,n=ep;  if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.1"};var o=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();if(void 0!==o&&(o.contextData.getValOnce="3.1"),window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){var n=window.location.hostname,o=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){o=2<o?o:2;var r=n.lastIndexOf(".");if(0<=r){for(;0<=r&&1<o;)r=n.lastIndexOf(".",r-1),o--;r=0<r?n.substring(r):n}}if(g=r,i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var f=new Date;f.setTime(f.getTime()+6e4*t)}else f=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),n=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>n?i.length:n)))?e:""},e){var i=i||"s_gvo",t=t||0,n="m"===n?6e4:864e5;if(e!==cookieRead(i)){var r=new Date;return r.setTime(r.getTime()+t*n),cookieWrite(i,e,0===t?0:r),e}}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getValOnce` La funzione utilizza i seguenti argomenti:

* **`vtc`** (obbligatorio, stringa): Variabile da controllare e vedere se è stata impostata in precedenza su un valore identico
* **`cn`** (facoltativo, stringa): Nome del cookie che contiene il valore da controllare. Predefinito su `"s_gvo"`
* **`et`** (facoltativo, numero intero): La scadenza del cookie in giorni (o minuti, a seconda del `ep` (argomento). Predefinito su `0`, che scade alla fine della sessione del browser
* **`ep`** (facoltativo, stringa): Imposta questo argomento solo se `et` viene impostato anche l&#39;argomento . Imposta questo argomento su `"m"` se vuoi `et` argomento che scade in minuti anziché in giorni. Predefinito su `"d"`, che imposta `et` argomento in giorni.

Se la `vtc` corrispondenza tra argomento e valore cookie, questa funzione restituisce una stringa vuota. Se la `vtc` il valore dell&#39;argomento e del cookie non corrisponde, la funzione restituisce il `vtc` come stringa.

## Esempi

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## Cronologia versioni

### 3.1 (22 settembre 2022)

* È stato corretto un bug per la scadenza

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.01

* È stato risolto un problema relativo alla scrittura di cookie.

### 2.0

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).

### 1.1

* È stata aggiunta l’opzione per scegliere minuti o giorni per la scadenza tramite la `t` parametro .
* Correzione dell&#39;ambito di applicazione `k` utilizzata solo per limitarla al plug-in. Questa modifica impedisce possibili interferenze con altro codice sulla pagina.
