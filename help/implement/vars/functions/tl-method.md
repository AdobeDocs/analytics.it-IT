---
title: tl
description: Invia una chiamata di tracciamento dei collegamenti ad Adobe.
feature: Appmeasurement Implementation
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 6%

---

# tl

Il metodo `tl()` è un importante componente di base di Adobe Analytics. Prende tutte le variabili Analytics definite sulla pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati di Adobe. Funziona in modo simile al metodo [`t()`](t-method.md), tuttavia questo metodo non incrementa le visualizzazioni di pagina. È utile per tenere traccia dei collegamenti e di altri elementi che non verrebbero considerati come caricamento di pagina completo.

Se [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) o [`trackExternalLinks`](../config-vars/trackexternallinks.md) sono abilitati, AppMeasurement chiama automaticamente il metodo `tl()` per inviare i dati di tracciamento del collegamento di download e di uscita. Se la tua organizzazione preferisce avere un maggiore controllo sui collegamenti da tracciare e sul loro comportamento, puoi chiamare manualmente il metodo `tl()`. I collegamenti personalizzati possono essere tracciati solo manualmente.

## Tracciamento dei collegamenti tramite Web SDK

Il Web SDK non distingue tra chiamate di visualizzazione pagina e chiamate di tracciamento dei collegamenti; entrambe utilizzano il comando `sendEvent`.

Se utilizzi un oggetto XDM e vuoi che Adobe Analytics conti un dato evento come chiamata di tracciamento dei collegamenti, assicurati che i dati XDM includano:

* Nome collegamento: mappato a `xdm.web.webInteraction.name`.
* URL collegamento: mappato a `xdm.web.webInteraction.URL`.
* Tipo di collegamento: mappato a `xdm.web.webInteraction.type`. I valori validi includono `other` (Collegamenti personalizzati), `download` (Collegamenti di download) e `exit` (Collegamenti di uscita).

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

Se utilizzi un oggetto dati e desideri che Adobe Analytics conti un dato evento come chiamata di tracciamento dei collegamenti, assicurati che l’oggetto dati includa:

* Nome collegamento: mappato a `data.__adobe.analytics.linkName`.
* URL collegamento: mappato a `data.__adobe.analytics.linkURL`.
* Tipo di collegamento: mappato a `data.__adobe.analytics.linkType`. I valori validi includono `o` (Collegamenti personalizzati), `d` (Collegamenti di download) e `e` (Collegamenti di uscita).

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "linkName": "My custom link",
        "linkURL": "https://example.com",
        "linkType": "o"
      }
    }
  }
});
```

## Tracciamento dei collegamenti tramite l’estensione Adobe Analytics

L&#39;estensione Adobe Analytics dispone di una posizione dedicata per impostare una chiamata di tracciamento dei collegamenti.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. In [!UICONTROL Actions], fare clic sull&#39;azione desiderata o sull&#39;icona **&#39;+&#39;** per aggiungere un&#39;azione.
1. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su **[!UICONTROL Adobe Analytics]** e [!UICONTROL Action Type] su **[!UICONTROL Send Beacon]**.
1. Fare clic sul pulsante di opzione `s.tl()`.

Non è possibile impostare argomenti facoltativi nell’estensione Analytics.

## Metodo s.tl() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiamare il metodo `s.tl()` quando si desidera inviare una chiamata di tracciamento ad Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Oggetto collegamento (obbligatorio)

L&#39;argomento oggetto link determina se il browser attende fino a 500 ms prima di uscire dalla pagina. Se una richiesta di immagine viene inviata prima di 500 ms, la pagina passa immediatamente al collegamento su cui è stato fatto clic.

>[!NOTE]
>
>AppMeasurement abilita automaticamente la variabile [`useBeacon`](../config-vars/usebeacon.md) per i collegamenti di uscita, rendendo questo argomento non più necessario nei browser moderni. Questo argomento è stato utilizzato più comunemente nelle versioni precedenti di AppMeasurement.

* `this`: attendi fino a 500 ms per consentire ad AppMeasurement di inviare una richiesta di immagine. Valore predefinito.
* `true`: Non attendere.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Tipo di collegamento (obbligatorio)

L’argomento tipo di collegamento è una stringa di un singolo carattere che determina il tipo di chiamata di tracciamento dei collegamenti. Sono disponibili tre valori validi.

* `o`: il collegamento è un [collegamento personalizzato](/help/components/dimensions/custom-link.md).
* `d`: il collegamento è un [collegamento di download](/help/components/dimensions/download-link.md).
* `e`: il collegamento è un [collegamento di uscita](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nome collegamento (consigliato)

L’argomento nome collegamento è una stringa che determina l’elemento della dimensione di tracciamento del collegamento. Quando si utilizzano le dimensioni [Collegamento personalizzato](/help/components/dimensions/custom-link.md), [Collegamento di download](/help/components/dimensions/download-link.md) o [Collegamento di uscita](/help/components/dimensions/exit-link.md) nel reporting, questa stringa contiene l&#39;elemento dimensione. Se questo argomento non è impostato, viene utilizzata la variabile [linkURL](../config-vars/linkurl.md).

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Override variabili (facoltative)

Consente di modificare i valori delle variabili per una singola chiamata. Per ulteriori informazioni, vedere [sostituzioni variabili](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Esempi e casi d’uso

Invia una chiamata di tracciamento dei collegamenti di base direttamente all’interno di un collegamento HTML:

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Utilizza JavaScript per effettuare una chiamata di tracciamento dei collegamenti di base utilizzando gli argomenti del metodo:

```JavaScript
s.tl(true,"o","Example link");
```

### Effettuare chiamate di tracciamento dei collegamenti all’interno di una funzione personalizzata

Puoi consolidare il codice di tracciamento dei collegamenti in una funzione JavaScript autonoma. È quindi possibile effettuare chiamate nella funzione `onClick` di ciascun collegamento. Imposta quanto segue in un file JavaScript:

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

Puoi quindi chiamare la funzione ogni volta che desideri tenere traccia di un determinato collegamento:

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

>[!NOTE]
>Una chiamata indiretta al metodo `tl()` può rendere meno pratico il reporting di sovrapposizione di Activity Map. È necessario fare clic su ogni collegamento per registrare la funzione con l&#39;elemento link. Tuttavia, le dimensioni di Activity Map in Workspace vengono tracciate allo stesso modo.

### Evita il tracciamento dei collegamenti duplicati

Se `trackDownloadLinks` o `trackExternalLinks` sono abilitati, AppMeasurement effettua automaticamente una chiamata di tracciamento dei collegamenti se i filtri corretti corrispondono. Se chiami anche manualmente `s.tl()` per questi clic di collegamento, puoi inviare dati duplicati ad Adobe. I dati duplicati gonfiano i numeri dei rapporti e li rendono meno precisi.

Ad esempio, la seguente funzione invierebbe due chiamate di tracciamento dei collegamenti per lo stesso clic di collegamento (collegamenti di download manuali e automatici):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Puoi evitare chiamate di tracciamento dei collegamenti duplicate utilizzando la seguente funzione modificata. Verifica innanzitutto se esiste un oggetto collegamento e invia una chiamata di tracciamento dei collegamenti manuale solo se l’oggetto collegamento è una stringa vuota.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```

### Utilizzare il metodo `tl()` con Activity Map

È possibile utilizzare il metodo `tl()` per tenere traccia degli elementi personalizzati e configurare il rendering della sovrapposizione per il contenuto dinamico. Il parametro `linkName` viene utilizzato anche per impostare la dimensione [Activity Map Link](/help/components/dimensions/activity-map-link.md).

Quando il metodo `tl()` viene chiamato direttamente dall&#39;evento al clic dell&#39;elemento HTML, Activity Map può visualizzare una sovrapposizione per tale elemento al caricamento della pagina Web. Ad esempio:

```html
<a href="index.html" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Quando il metodo `tl()` non viene chiamato direttamente dall&#39;evento al clic dell&#39;elemento HTML, Activity Map può visualizzare una sovrapposizione solo dopo aver fatto clic su tale elemento. Ad esempio:

```html
<a href="index.html" onclick="someFn(event);">Example link text</a>
<script>
  function someFn (event) {
    s.tl(event.srcElement,'o','Example custom link');
  }
</script>
```
