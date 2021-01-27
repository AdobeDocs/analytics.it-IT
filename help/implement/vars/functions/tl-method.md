---
title: tl
description: Invia una chiamata di tracciamento dei collegamenti a  Adobe.
translation-type: tm+mt
source-git-commit: 5bdd07b147d1ea5ef80336a893c02057e7bf5785
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 0%

---


# tl

Il metodo `tl()` è un componente di base importante per  Adobe Analytics. Prende tutte le variabili Analytics definite nella pagina, le compila in una richiesta di immagine e invia tali dati  server di raccolta dati di Adobe. Funziona in modo simile al metodo [`t()`](t-method.md), tuttavia questo metodo non incrementa le visualizzazioni di pagina. È utile per tenere traccia dei collegamenti e di altri elementi che non verrebbero considerati un caricamento di pagina completo.

Se sono abilitati [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) o [`trackExternalLinks`](../config-vars/trackexternallinks.md), AppMeasurement chiama automaticamente il metodo `tl()` per inviare i dati di tracciamento dei collegamenti di download e di uscita. Se l&#39;organizzazione preferisce avere maggiore controllo sui collegamenti da monitorare e sul loro comportamento, puoi chiamare manualmente il metodo `tl()`. I collegamenti personalizzati possono essere tracciati solo manualmente.

## Chiamata di tracciamento dei collegamenti in  Adobe Experience Platform Launch

Launch ha una posizione dedicata impostata come chiamata di tracciamento dei collegamenti.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Passate alla scheda [!UICONTROL Rules], quindi fate clic sulla regola desiderata (o create una regola).
1. In [!UICONTROL Actions] fare clic sull&#39;icona &quot;+&quot;
1. Impostate il menu a discesa [!UICONTROL Extension] su  Adobe Analytics e [!UICONTROL Action Type] su Invia beacon.
1. Fare clic sul pulsante di scelta `s.tl()`.

Non è possibile impostare argomenti facoltativi in Launch.

## s.tl() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Chiama il metodo `s.tl()` per inviare una chiamata di tracciamento al Adobe .

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Oggetto Link (obbligatorio)

L&#39;argomento dell&#39;oggetto link determina se il browser attende fino a 500 ms prima di uscire dalla pagina. Se una richiesta di immagine viene inviata prima di 500 ms, la pagina passa immediatamente al collegamento selezionato.

>[!NOTE]
>
>AppMeasurement abilita automaticamente la variabile [`useBeacon`](../config-vars/usebeacon.md) per i collegamenti di uscita, rendendo questo argomento non più necessario nei browser moderni. Questo argomento è stato utilizzato più frequentemente nelle versioni precedenti di AppMeasurement.

* `this`: Attendi fino a 500 ms per concedere ad AppMeasurement il tempo necessario per inviare una richiesta di immagine. Valore predefinito.
* `true`: Non aspettate.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Tipo di collegamento (richiesto)

L’argomento tipo di collegamento è una stringa a carattere singolo che determina il tipo di chiamata di tracciamento dei collegamenti. Esistono tre valori validi.

* `o`: Il collegamento è un collegamento [ ](/help/components/dimensions/custom-link.md)personalizzato.
* `d`: Il collegamento è un collegamento  [Scarica](/help/components/dimensions/download-link.md).
* `e`: Il collegamento è un collegamento [ ](/help/components/dimensions/exit-link.md)Exit (Esci).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nome collegamento (consigliato)

L’argomento del nome del collegamento è una stringa che determina l’elemento della dimensione di tracciamento del collegamento. Quando si utilizzano le dimensioni [Collegamento personalizzato](/help/components/dimensions/custom-link.md), [Collegamento di download](/help/components/dimensions/download-link.md) o [Collegamento di uscita](/help/components/dimensions/exit-link.md) nel reporting, questa stringa contiene l&#39;elemento dimensione. Se questo argomento non è impostato, viene utilizzata la variabile [linkURL](../config-vars/linkurl.md).

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Sostituzioni delle variabili (facoltative)

Consente di modificare i valori variabili per una singola chiamata. Per ulteriori informazioni, vedere [sostituzioni variabili](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Esempi e casi di utilizzo

Invia una chiamata di tracciamento dei collegamenti di base direttamente all’interno di un collegamento HTML:

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Utilizza JavaScript per effettuare una chiamata di tracciamento dei collegamenti di base utilizzando gli argomenti dei metodi:

```JavaScript
s.tl(true,"o","Example link");
```

### Effettuare chiamate di tracciamento dei collegamenti all&#39;interno di una funzione personalizzata

È possibile consolidare il codice di tracciamento dei collegamenti in una funzione JavaScript indipendente definita sulla pagina o in un file JavaScript collegato. È quindi possibile effettuare chiamate nella funzione onClick di ogni collegamento. Impostate quanto segue in un file JavaScript:

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

È quindi possibile chiamare la funzione ogni volta che si desidera tenere traccia di un determinato collegamento:

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### Evitare il tracciamento di collegamenti duplicati

Se sono abilitati `trackDownloadLinks` o `trackExternalLinks`, AppMeasurement effettua automaticamente una chiamata di tracciamento dei collegamenti se i filtri corretti corrispondono. Se si chiama anche manualmente `s.tl()` per questi clic di collegamento, è possibile inviare dati duplicati a  Adobe. I dati duplicati aumentano i numeri dei rapporti e li rendono meno precisi.

Ad esempio, la funzione seguente invierebbe due chiamate di tracciamento dei collegamenti per lo stesso clic (collegamenti per il download manuale e automatico):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Puoi evitare chiamate di tracciamento dei collegamenti duplicate utilizzando la seguente funzione modificata. Innanzitutto controlla se esiste un oggetto collegamento e invia una chiamata di tracciamento dei collegamenti manuale solo se l’oggetto collegamento è una stringa vuota.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
