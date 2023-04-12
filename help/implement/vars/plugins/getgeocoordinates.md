---
title: getGeoCoordinates
description: Monitora la geolocalizzazione di un visitatore.
feature: Variables
exl-id: 8620d083-7fa6-432b-891c-e24907e7c466
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 10%

---

# Plug-in di Adobe: getGeoCoordinates

{{plug-in}}

La `getGeoCoordinates` Il plug-in consente di acquisire la latitudine e la longitudine dei dispositivi dei visitatori. Adobe consiglia di utilizzare questo plug-in se desideri acquisire dati di geolocalizzazione nelle variabili di Analytics.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con l’SDK per web.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic su **[!UICONTROL Tags]** a sinistra, quindi fai clic sulla proprietà tag desiderata.
1. Fai clic su **[!UICONTROL Extensions]** a sinistra, quindi fai clic sul pulsante **[!UICONTROL Catalog]** scheda
1. Individua e installa il **[!UICONTROL Common Web SDK Plugins]** estensione.
1. Fai clic su **[!UICONTROL Data Elements]** a sinistra, quindi fai clic sull’elemento dati desiderato.
1. Imposta il nome dell&#39;elemento dati desiderato con la seguente configurazione:
   * Estensione: Plug-in SDK per web comuni
   * Elemento dati: `getGeoCoordinates`
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
   * Tipo azione: Inizializza getGeoCoordinates
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
/* Adobe Consulting Plugin: getGeoCoordinates v2.0  */
function getGeoCoordinates(){if(arguments&&"-v"===arguments[0])return{plugin:"getGeoCoordinates",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getGeoCoordinates="2.0");window.cookieWrite=window.cookieWrite||function(a,c,f){if("string"===typeof a){var h=window.location.hostname,b=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){b=2<b?b:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<b;)e=h.lastIndexOf(".",e-1),b--;e=0<e?h.substring(e):h}}g=e;c="undefined"!==typeof c?""+c:"";if(f||""===c)if(""===c&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(c)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===c:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var c=" "+document.cookie,b=c.indexOf(" "+a+"="),d=0>b?b:c.indexOf(";",b);return(a=0>b?"":decodeURIComponent(c.substring(b+2+a.length,0>d?c.length:d)))?a:""};var d="";b=cookieRead("s_ggc").split("|");var k={timeout:5E3,maximumAge:0},l=function(a){a=a.coords;cookieWrite("s_ggc",parseFloat(a.latitude.toFixed(4))+"|"+parseFloat(a.longitude.toFixed(4)),30);d="latitude="+parseFloat(a.latitude.toFixed(4))+" | longitude="+parseFloat(a.longitude.toFixed(4))},m=function(a){d="error retrieving geo coordinates"};1<b.length&&(d="latitude="+b[0]+" | longitude="+b[1]);navigator.geolocation&&navigator.geolocation.getCurrentPosition(l,m,k);""===d&&(d="geo coordinates not available");return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getGeoCoordinates` La funzione non utilizza argomenti. Restituisce uno dei seguenti valori:

* `"geo coordinates not available"`: Per i dispositivi che non dispongono di dati di geolocalizzazione al momento dell&#39;esecuzione del plug-in. Questo valore è comune per il primo hit della visita, soprattutto quando i visitatori hanno bisogno del consenso per tracciare la propria posizione.
* `"error retrieving geo coordinates"`: Quando il plug-in rileva errori durante il tentativo di recupero della posizione del dispositivo
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Dove [LATITUDINE]/[LONGITUDINE] sono rispettivamente latitudine e longitudine

>[!NOTE]
>
>I valori delle coordinate vengono arrotondati al quarto decimale più vicino. Ad esempio, il valore di `"40.438635333"` viene arrotondato a `"40.4386"` per limitare il numero di valori univoci da acquisire. I valori sono abbastanza vicini da identificare la posizione esatta del dispositivo a circa 20 piedi.

Questo plug-in utilizza un cookie denominato `"s_ggc"` per memorizzare le coordinate tra i risultati, se necessario.

## Esempi

```js
// Sets eVar1 to one of the above return values depending on the visitor's device status.
s.eVar1 = getGeoCoordinates();

// Extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications.
var coordinates = getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}

// From there, you can determine whether a visitor is at, for example, the Statue of Liberty:
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongitude >= -74.0446 && finalLongitude <= -74.0444)
{
  var visitorAtStatueOfLiberty = true;
}
else
{
  var visitorAtStatueOfLiberty = false;
}
```

## Cronologia versioni

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (25 maggio 2015)

* Versione iniziale.
