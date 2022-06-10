---
title: tl
description: Invia ad Adobe una chiamata di tracciamento dei collegamenti.
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 0%

---

# tl

La `tl()` è un componente di base importante per Adobe Analytics. Prende tutte le variabili Analytics definite nella pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati di Adobe. Funziona in modo simile al [`t()`](t-method.md) , tuttavia questo metodo non incrementa le visualizzazioni di pagina. È utile per tenere traccia dei collegamenti e di altri elementi che non verrebbero considerati come un caricamento completo della pagina.

Se [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) o [`trackExternalLinks`](../config-vars/trackexternallinks.md) sono abilitati, AppMeasurement chiama automaticamente il `tl()` metodo per inviare i dati di tracciamento dei collegamenti di download e di uscita. Se la tua organizzazione preferisce avere più controllo sui collegamenti da tracciare e sul loro comportamento, puoi chiamare il `tl()` metodo manuale. I collegamenti personalizzati possono essere tracciati solo manualmente.

## Tracciamento dei collegamenti tramite l’SDK per web

L&#39;SDK per web non distingue tra le chiamate di visualizzazione della pagina e quelle di tracciamento dei collegamenti; entrambi utilizzano `sendEvent` comando. Se desideri che Adobe Analytics conti un dato evento come una chiamata di tracciamento dei collegamenti, assicurati che i dati XDM includano `web.webInteraction.name`, `web.webInteraction.URL`e `web.webInteraction.type`.

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

## Tracciamento dei collegamenti tramite l’estensione Adobe Analytics

L’estensione Adobe Analytics dispone di una posizione dedicata per impostare una chiamata di tracciamento dei collegamenti.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
1. Sotto [!UICONTROL Actions], fai clic sull’azione desiderata o fai clic sul pulsante **&#39;+&#39;** per aggiungere un’azione.
1. Imposta la [!UICONTROL Extension] a discesa **[!UICONTROL Adobe Analytics]** e [!UICONTROL Action Type] a **[!UICONTROL Send Beacon]**.
1. Fai clic sul pulsante `s.tl()` pulsante di scelta.

Non è possibile impostare argomenti facoltativi nell’estensione Analytics.

## s.tl() in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

Chiama il `s.tl()` quando desideri inviare una chiamata di tracciamento ad Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Oggetto Link (obbligatorio)

L’argomento dell’oggetto collegamento determina se il browser attende fino a 500 ms prima di spostarsi dalla pagina. Se una richiesta di immagine viene inviata prima di 500 ms, la pagina passa immediatamente al collegamento selezionato.

>[!NOTE]
>
>AppMeasurement abilita automaticamente il [`useBeacon`](../config-vars/usebeacon.md) per i collegamenti di uscita, rendendo questo argomento non più necessario nei browser moderni. Questo argomento è stato utilizzato più comunemente nelle versioni precedenti di AppMeasurement.

* `this`: Attendi fino a 500 ms per dare tempo ad AppMeasurement per inviare una richiesta di immagine. Valore predefinito.
* `true`: Non aspettare.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Tipo di collegamento (obbligatorio)

L’argomento tipo di collegamento è una stringa a carattere singolo che determina il tipo di chiamata di tracciamento del collegamento. Tre valori validi.

* `o`: Il collegamento è un [Collegamento personalizzato](/help/components/dimensions/custom-link.md).
* `d`: Il collegamento è un [Collegamento di download](/help/components/dimensions/download-link.md).
* `e`: Il collegamento è un [Collegamento di uscita](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nome collegamento (consigliato)

L’argomento nome collegamento è una stringa che determina l’elemento della dimensione di tracciamento del collegamento. Quando utilizzi [Collegamento personalizzato](/help/components/dimensions/custom-link.md), [Collegamento di download](/help/components/dimensions/download-link.md)oppure [Collegamento di uscita](/help/components/dimensions/exit-link.md) dimensioni nel reporting, questa stringa contiene l&#39;elemento dimensione. Se questo argomento non viene impostato, il [linkURL](../config-vars/linkurl.md) viene utilizzata la variabile .

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Ignorare le variabili (facoltativo)

Consente di modificare i valori delle variabili per una singola chiamata. Vedi [sostituzioni delle variabili](../../js/overrides.md) per ulteriori informazioni.

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

### Effettuare chiamate di tracciamento dei collegamenti all’interno di una funzione personalizzata

Puoi consolidare il codice di tracciamento dei collegamenti in una funzione JavaScript indipendente definita sulla pagina o in un file JavaScript collegato. È quindi possibile effettuare chiamate nella funzione onClick di ogni collegamento. Imposta quanto segue in un file JavaScript:

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

### Evita di tracciare i collegamenti duplicati

Se `trackDownloadLinks` o `trackExternalLinks` sono abilitati, AppMeasurement effettua automaticamente una chiamata di tracciamento dei collegamenti se i filtri corretti corrispondono. Se si chiama anche manualmente `s.tl()` per questi clic sul collegamento, puoi inviare dati duplicati ad Adobe. I dati duplicati gonfiano i numeri dei rapporti e li rendono meno precisi.

Ad esempio, la funzione seguente invierebbe due chiamate di tracciamento dei collegamenti per lo stesso clic (collegamenti per il download manuale e automatico):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Puoi evitare chiamate di tracciamento dei collegamenti duplicate utilizzando la seguente funzione modificata. In primo luogo controlla se esiste un oggetto collegamento e invia una chiamata di tracciamento dei collegamenti manuale solo se l&#39;oggetto collegamento è una stringa vuota.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
