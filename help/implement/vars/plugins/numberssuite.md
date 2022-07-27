---
title: Suite numeri
description: Produrre e manipolare numeri da utilizzare in altre variabili JavaScript.
feature: Variables
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 1%

---

# Plug-in di Adobe: Suite numeri

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

I numeri Suite una serie di funzioni JavaScript. Include i seguenti plug-in:

* **`zeroPad`**: Aggiungi un numero specifico di zeri all&#39;inizio di un numero. Questo plug-in è utile se una variabile richiede un certo numero di cifre, ad esempio se si lavora con oggetti data JavaScript e si desidera formattare il mese e il giorno di una data con due cifre invece di una sola cifra. Ad esempio: `01/09/2020` anziché `1/9/2020`.
* **`randomNumber`**: Genera un numero casuale con un numero specifico di cifre. Questo plug-in è utile se distribuisci tag di terze parti e desideri un numero casuale di cache non compatibile.
* **`twoDecimals`**: Girare un numero fino alla centesima. Questo plug-in è utile a scopo di valuta, consentendoti di arrotondare un numero a un valore di valuta valido.

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
    * Action Type: Initialize Numbers Suite
1. Save and publish the changes to the rule.-->

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
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare i plug-in

La `zeroPad` La funzione utilizza i seguenti argomenti:

* **num** (obbligatorio, numero intero): Numero da aggiungere al pad. La funzione arrotonda il valore di questo argomento se contiene decimali.
* **cenno** (obbligatorio, numero intero): Numero di cifre nel valore finale restituito. Se il numero da aggiungere ha meno cifre del numero di cifre a cui aggiungere il pad, il plug-in aggiunge zeri all&#39;inizio della `num` argomento.

La `randomNumber` La funzione utilizza i seguenti argomenti:

* **cenno** (facoltativo, numero intero): Il numero di cifre nel numero casuale che si desidera generare. Il valore massimo è di 17 cifre. Il valore predefinito è 10 cifre.

La `twoDecimals` La funzione utilizza i seguenti argomenti:

* **val** (obbligatorio, numero): Un numero (rappresentato da una stringa o un oggetto numerico) che si desidera arrotondare al centesimo più vicino.

## Restituisce

* La **zeroPad** restituisce una stringa uguale a `num` argomento ma con un numero specifico di zeri aggiunti all&#39;inizio del suo valore, in modo che il valore restituito abbia il numero corretto di cifre.
* La **randomNumber** restituisce una stringa uguale a un numero casuale con il numero desiderato di cifre.
* La **dueDecimali** restituisce un numero di oggetto arrotondato al centesimo più vicino.

## Chiamate di esempio

### esempi di zeroPad

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### esempi randomNumber

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### esempi dueDecimals

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Cronologia versioni

### 1.0 (25 maggio 2019)

* Versione iniziale.
