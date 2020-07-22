---
title: tl
description: Invia una chiamata di tracciamento dei collegamenti ad Adobe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 1%

---


# tl

Il `tl()` metodo è un componente di base importante per Adobe  Analytics. Prende tutte  variabili Analytics definite nella pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati Adobe. Funziona in modo simile al [`t()`](t-method.md) metodo, ma questo metodo non incrementa le visualizzazioni di pagina. È utile per tenere traccia dei collegamenti e di altri elementi che non verrebbero considerati un caricamento di pagina completo.

Se [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) o [`trackExternalLinks`](../config-vars/trackexternallinks.md) sono abilitati, AppMeasurement chiama automaticamente il `tl()` metodo per inviare i dati di tracciamento dei collegamenti di download e di uscita. Se l&#39;organizzazione preferisce avere maggiore controllo sui collegamenti da monitorare e sul loro comportamento, puoi chiamare il `tl()` metodo manualmente. I collegamenti personalizzati possono essere tracciati solo manualmente.

## Chiamata di tracciamento dei collegamenti in  Adobe Experience Platform Launch

Launch ha una posizione dedicata impostata come chiamata di tracciamento dei collegamenti.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
1. In [!UICONTROL Actions], fare clic sull&#39;icona &quot;+&quot;
1. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e su [!UICONTROL Action Type] Invia beacon.
1. Click the `s.tl()` radio button.

Non è possibile impostare argomenti facoltativi in Launch.

## s.tl() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Chiama il `s.tl()` metodo per inviare una chiamata di tracciamento ad Adobe.

```js
s.tl();
```

Facoltativamente, questo metodo accetta diversi argomenti:

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Oggetto link

L&#39;argomento dell&#39;oggetto link determina se il browser attende fino a 500 ms prima di uscire dalla pagina. Se una richiesta di immagine viene inviata prima di 500 ms, la pagina passa immediatamente al collegamento selezionato.

>[!NOTE]
>
>AppMeasurement abilita automaticamente la [`useBeacon`](../config-vars/usebeacon.md) variabile per i collegamenti di uscita, rendendo questo argomento non più necessario nei browser moderni. Questo argomento è stato utilizzato più frequentemente nelle versioni precedenti di AppMeasurement.

* `this`: Attendi fino a 500 ms per concedere ad AppMeasurement il tempo necessario per inviare una richiesta di immagine. Valore predefinito.
* `true`: Non aspettate.

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### Tipo di collegamento

L’argomento del tipo di collegamento è una stringa a lettera singola che determina il tipo di chiamata di tracciamento dei collegamenti. È la stessa impostazione della [`linkType`](../config-vars/linktype.md) variabile.

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### Nome collegamento

L’argomento del nome del collegamento è una stringa che determina l’elemento della dimensione di tracciamento del collegamento. È la stessa impostazione della [`linkName`](../config-vars/linkname.md) variabile.

```js
s.tl(true,"d","Example download link");
```

### Override variabili

Consente di modificare i valori variabili per una singola chiamata. Per ulteriori informazioni, vedi [sostituzioni](../../js/overrides.md) variabili.

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

Utilizza JavaScript per effettuare la stessa chiamata di base per il tracciamento dei collegamenti utilizzando variabili separate:

```js
s.linkType = "o";
s.linkName = "Example link";
s.tl();
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

Se `trackDownloadLinks` o `trackExternalLinks` sono abilitati, AppMeasurement effettua automaticamente una chiamata di tracciamento dei collegamenti se i filtri corretti corrispondono. Se richiamate manualmente `s.tl()` questi clic di collegamento, potete inviare dati duplicati ad Adobe. I dati duplicati aumentano i numeri dei rapporti e li rendono meno precisi.

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
