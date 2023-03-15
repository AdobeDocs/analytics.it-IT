---
title: tl
description: Invia una chiamata di tracciamento dei collegamenti ad Adobe.
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
source-git-commit: 8ff414efff302adfee42f192e781a8dec5c42902
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 6%

---

# tl

Il `tl()` Il metodo è un componente core importante per Adobe Analytics. Prende tutte le variabili di Analytics definite sulla pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati di Adobe. Funziona in modo simile al [`t()`](t-method.md) Tuttavia, questo metodo non incrementa le visualizzazioni di pagina. È utile per tenere traccia dei collegamenti e di altri elementi che non verrebbero considerati come caricamento di pagina completo.

Se [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) o [`trackExternalLinks`](../config-vars/trackexternallinks.md) , AppMeasurement chiama automaticamente il `tl()` metodo per inviare i dati di tracciamento dei collegamenti di download e di uscita. Se la tua organizzazione preferisce avere un maggiore controllo sui collegamenti da tracciare e sul loro comportamento, puoi chiamare il `tl()` manuale. I collegamenti personalizzati possono essere tracciati solo manualmente.

## Tracciamento dei collegamenti tramite Web SDK

L’SDK per web non distingue tra chiamate di visualizzazione pagina e chiamate di tracciamento dei collegamenti; entrambe utilizzano `sendEvent` comando. Se vuoi che Adobe Analytics conti un dato evento XDM come chiamata di tracciamento dei collegamenti, assicurati che i dati XDM includano o siano mappati su `web.webInteraction.name`, `web.webInteraction.URL`, e `web.webInteraction.type`.

* Il nome del collegamento è associato a `web.webInteraction.name`.
* Collega URL mappato a `web.webInteraction.URL`.
* Il tipo di collegamento è associato a `web.webInteraction.type`. I valori validi includono `other` (Collegamenti personalizzati), `download` (Collegamenti di download) e `exit` (Collegamenti di uscita).

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

L&#39;estensione Adobe Analytics dispone di una posizione dedicata per impostare una chiamata di tracciamento dei collegamenti.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. Sotto [!UICONTROL Actions], fai clic sull’azione desiderata o fai clic su **&#39;+&#39;** per aggiungere un&#39;azione.
1. Imposta il [!UICONTROL Extension] menu a discesa per **[!UICONTROL Adobe Analytics]** e [!UICONTROL Action Type] a **[!UICONTROL Send Beacon]**.
1. Fai clic su `s.tl()` pulsante di opzione.

Non è possibile impostare argomenti facoltativi nell’estensione Analytics.

## Metodo s.tl() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.tl()` quando desideri inviare una chiamata di tracciamento ad Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Oggetto collegamento (obbligatorio)

L&#39;argomento oggetto link determina se il browser attende fino a 500 ms prima di uscire dalla pagina. Se una richiesta di immagine viene inviata prima di 500 ms, la pagina passa immediatamente al collegamento su cui è stato fatto clic.

>[!NOTE]
>
>AppMeasurement abilita automaticamente [`useBeacon`](../config-vars/usebeacon.md) variabile per i collegamenti di uscita, rendendo questo argomento non più necessario nei browser moderni. Questo argomento è stato utilizzato più comunemente nelle versioni precedenti di AppMeasurement.

* `this`: attendi fino a 500 ms per concedere ad AppMeasurement il tempo necessario per inviare una richiesta di immagine. Valore predefinito.
* `true`: non aspettare.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Tipo di collegamento (obbligatorio)

L’argomento tipo di collegamento è una stringa di un singolo carattere che determina il tipo di chiamata di tracciamento dei collegamenti. Sono disponibili tre valori validi.

* `o`: il collegamento è un [Collegamento personalizzato](/help/components/dimensions/custom-link.md).
* `d`: il collegamento è un [Collegamento di download](/help/components/dimensions/download-link.md).
* `e`: il collegamento è un [Collegamento di uscita](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nome collegamento (consigliato)

L’argomento nome collegamento è una stringa che determina l’elemento della dimensione di tracciamento del collegamento. Quando si utilizza [Collegamento personalizzato](/help/components/dimensions/custom-link.md), [Collegamento di download](/help/components/dimensions/download-link.md), o [Collegamento di uscita](/help/components/dimensions/exit-link.md) dimensioni nel reporting, questa stringa contiene l’elemento dimensione. Se questo argomento non è impostato, il [linkURL](../config-vars/linkurl.md) viene utilizzata la variabile.

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Override variabili (facoltative)

Consente di modificare i valori delle variabili per una singola chiamata. Consulta [sostituzioni variabili](../../js/overrides.md) per ulteriori informazioni.

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

Puoi consolidare il codice di tracciamento dei collegamenti in una funzione JavaScript indipendente definita nella pagina o in un file JavaScript collegato. È quindi possibile effettuare chiamate nella funzione onClick di ciascun collegamento. Imposta quanto segue in un file JavaScript:

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

### Evita il tracciamento dei collegamenti duplicati

Se `trackDownloadLinks` o `trackExternalLinks` Se i filtri corretti corrispondono, AppMeasurement effettua automaticamente una chiamata di tracciamento dei collegamenti. Se richiami anche manualmente `s.tl()` per questi clic sui collegamenti, puoi inviare dati duplicati ad Adobe. I dati duplicati gonfiano i numeri dei rapporti e li rendono meno precisi.

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
