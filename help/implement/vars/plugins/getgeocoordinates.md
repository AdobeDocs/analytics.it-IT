---
title: getGeoCoordinates
description: Monitora la geolocalità di un visitatore.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 1%

---


# Plug-in Adobe: getGeoCoordinates

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getGeoCoordinates` plug-in consente di acquisire la latitudine e la longitudine dei dispositivi dei visitatori. Adobe consiglia di utilizzare questo plug-in per acquisire i dati di geolocalizzazione  variabili Analytics.

## Installare il plug-in utilizzando l&#39;estensione Lancio del Adobe Experience Platform 

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in Analytics  comuni
   * Tipo azione: Inizializza getGeoCoordinates
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe  Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata un&#39;istanza dell&#39;oggetto di tracciamento Analytics  (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getGeoCoordinates` metodo non utilizza argomenti. Restituisce uno dei seguenti valori:

* `"geo coordinates not available"`: Per i dispositivi che non dispongono di dati di geolocalizzazione al momento dell&#39;esecuzione del plug-in. Questo valore è comune per il primo hit della visita, soprattutto quando i visitatori devono fornire il consenso al tracciamento della loro posizione.
* `"error retrieving geo coordinates"`: Quando il plug-in rileva errori durante il tentativo di recuperare la posizione del dispositivo
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Dove [LATITUDINE]/[LONGITUDINE] sono rispettivamente la latitudine e la longitudine

>[!NOTE]
>
>I valori delle coordinate vengono arrotondati al quarto decimale più vicino. Ad esempio, il valore di `"40.438635333"` viene arrotondato per `"40.4386"` limitare il numero di valori univoci da acquisire. I valori sono abbastanza vicini da identificare la posizione esatta del dispositivo a circa 20 piedi.

Questo plug-in utilizza un cookie denominato `"s_ggc"` per memorizzare le coordinate tra gli hit, se necessario.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.eVar1 = s.getGeoCoordinates();
```

...imposta eVar1 uguale a uno dei valori restituiti sopra a seconda dello stato del dispositivo del visitatore

### Esempio n. 2

Il codice seguente estrae latitudine e longitudine nelle proprie variabili denominate finalLatitude e finalLongitude per l’utilizzo in altri codici/applicazioni

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

Da qui potete determinare se un visitatore si trova, ad esempio, nella Statua della Libertà:

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## Cronologia versioni

### 1.0 (25 maggio 2015)

* Versione iniziale.
