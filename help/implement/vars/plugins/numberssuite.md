---
title: Numbers Suite
description: Produrre e manipolare numeri da utilizzare in altre variabili JavaScript.
feature: Variables
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 5%

---

# Plug-in di Adobe: suite di numeri

{{plug-in}}

La Numbers Suite dispone di una serie di funzioni JavaScript. Include i seguenti plug-in:

* **`zeroPad`**: aggiungi un numero specifico di zeri all’inizio di un numero. Questo plug-in è utile se una variabile richiede un determinato numero di cifre, ad esempio se si utilizzano oggetti data JavaScript e si desidera formattare il mese e il giorno di una data con due cifre anziché con una sola cifra. Ad esempio: `01/09/2020` invece di `1/9/2020`.
* **`randomNumber`**: genera un numero casuale con un numero specifico di cifre. Questo plug-in è utile se distribuisci tag di terze parti e desideri un numero casuale di cache non funzionante.
* **`twoDecimals`**: Arrotonda un numero al centesimo dell’armadio. Questo plug-in è utile a scopo di valuta, consentendoti di arrotondare un numero a un valore di valuta valido.

## Installare il plug-in utilizzando l’estensione Web SDK o Web SDK

Questo plug-in non è ancora supportato per l’utilizzo nell’SDK per web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sul pulsante [!UICONTROL Catalog] pulsante
1. Installare e pubblicare [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Initialize Plug-ins&quot; (Inizializza plug-in) con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Library Loaded (Page Top)
1. Aggiungi un’azione alla regola precedente con la seguente configurazione:
   * Estensione: Common Analytics Plugins
   * Tipo azione: inizializza suite numeri
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi [!UICONTROL Configure tracking using custom code] Pannello a soffietto, che mostra [!UICONTROL Open Editor] pulsante.
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file di AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

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

Il `zeroPad` La funzione utilizza i seguenti argomenti:

* **num** (obbligatorio, numero intero): numero da aggiungere. La funzione arrotonda il valore di questo argomento per difetto se contiene decimali.
* **annuire** (obbligatorio, numero intero): numero di cifre nel valore restituito finale. Se il numero da aggiungere ha meno cifre del numero di cifre da aggiungere, il plug-in aggiunge zeri all&#39;inizio del `num` argomento.

Il `randomNumber` La funzione utilizza i seguenti argomenti:

* **annuire** (facoltativo, numero intero): numero di cifre nel numero casuale che si desidera generare. Il valore massimo è di 17 cifre. Il valore predefinito è 10 cifre.

Il `twoDecimals` La funzione utilizza i seguenti argomenti:

* **val** (obbligatorio, numero): numero (rappresentato da una stringa o da un oggetto numero) che si desidera arrotondare al centesimo più vicino.

## Restituisce

* Il **zeroPad** funzione restituisce una stringa uguale al valore `num` ma con un numero specifico di zeri aggiunti all&#39;inizio del relativo valore, in modo che il valore restituito abbia il numero corretto di cifre.
* Il **randomNumber** La funzione restituisce una stringa uguale a un numero casuale con il numero di cifre desiderato.
* Il **twoDecimals** La funzione restituisce un oggetto number arrotondato al centesimo più vicino.

## Esempio di chiamate

### esempi di zeroPad

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber, esempi

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
