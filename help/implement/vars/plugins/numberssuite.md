---
title: Suite numeri
description: Produrre e manipolare i numeri da utilizzare in altre variabili JavaScript.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 1%

---


# Plug-in Adobe: Suite numeri

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Numeri Suite una serie di funzioni JavaScript. Include i seguenti plug-in:

* **`zeroPad`**: Aggiungete un numero specifico di zeri all&#39;inizio di un numero. Questo plug-in è utile se una variabile richiede un certo numero di cifre, ad esempio se si lavora con oggetti data JavaScript e si desidera formattare il mese e il giorno di una data con due cifre invece di una sola cifra. Ad esempio, `01/09/2020` anziché `1/9/2020`.
* **`randomNumber`**: Genera un numero casuale con un numero specifico di cifre. Questo plug-in è utile se distribuite tag di terze parti e desiderate un numero casuale con cache-busting.
* **`twoDecimals`**: Arrotondare un numero al centesimo più vicino. Questo plug-in è utile a scopo valutario e consente di arrotondare un numero a un valore di valuta valido.

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
   * Tipo azione: Inizializza suite di numeri
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare i plug-in

Il `zeroPad` metodo utilizza i seguenti argomenti:

* **num** (obbligatorio, numero intero): Numero da aggiungere al pad. Il metodo arrotonda il valore di questo argomento se contiene decimali.
* **nod** (obbligatorio, numero intero): Il numero di cifre nel valore restituito finale. Se il numero del tastierino contiene meno cifre del numero di cifre a cui aggiungere il pad, il plug-in aggiunge zeri all&#39;inizio dell&#39; `num` argomento.

Il `randomNumber` metodo utilizza i seguenti argomenti:

* **nod** (facoltativo, numero intero): Il numero di cifre nel numero casuale che si desidera generare. Il valore massimo è 17 cifre. Il valore predefinito è 10 cifre.

Il `twoDecimals` metodo utilizza i seguenti argomenti:

* **val** (obbligatorio, numero): Un numero (rappresentato da una stringa o un oggetto numero) che si desidera arrotondare al centesimo più vicino.

## Restituisce

* Il metodo **zeroPad** restituisce una stringa uguale all&#39; `num` argomento ma con un numero specifico di zeri aggiunti all&#39;inizio del relativo valore, in modo che il valore restituito abbia il numero corretto di cifre.
* Il metodo **randomNumber** restituisce una stringa uguale a un numero casuale con il numero desiderato di cifre.
* Il metodo **twoDecimals** restituisce un oggetto numero arrotondato al centesimo più vicino.

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

### esempi twoDecimals

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Cronologia versioni

### 1.0 (25 maggio 2019)

* Versione iniziale.
