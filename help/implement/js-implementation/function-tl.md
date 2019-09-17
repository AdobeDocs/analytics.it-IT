---
description: I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in AppMeasurement per il file JavaScript.
keywords: Implementazione di Analytics
seo-description: I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in AppMeasurement per il file JavaScript.
seo-title: 'Funzione s.tl(): tracciamento dei collegamenti'
solution: Analytics
subtopic: Tracciamento dei collegamenti
title: 'Funzione s.tl(): tracciamento dei collegamenti'
topic: Sviluppatore e implementazione
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 1ed1c6cd3fd6d29fa156cd4b2c4bdfe9120b3c61

---


# Funzione s.tl(): tracciamento dei collegamenti

Se l'organizzazione preferisce avere maggiore controllo sui collegamenti da monitorare e sul loro comportamento, si consiglia di effettuare il tracciamento manuale dei collegamenti. Utilizza la funzione s.tl() per inviare manualmente le richieste di tracciamento dei collegamenti con il contenuto esatto desiderato. Se il tracciamento dei collegamenti di base è tutto ciò che è necessario, consulta `s.trackDownloadLinks` e `s.trackExitLinks` in Variabili [di](c-variables/configuration-variables.md)configurazione. I collegamenti personalizzati non possono essere tracciati automaticamente.

> [!NOTE] Il codice di tracciamento dei collegamenti è spesso molto specifico per il tuo sito e per le esigenze di reporting. Adobe consiglia un’esperienza di implementazione o un consulente per l’implementazione per comprendere come utilizzare questa funzione in base alle esigenze aziendali.

## Sintassi ed esempi

Sintassi di base:

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

Esempi di base:

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true (obbligatorio)

Il primo argomento determina se il browser attende fino a 500 ms prima di spostarsi lontano dalla pagina. Se una richiesta di immagine viene inviata prima di 500 ms, la pagina passa immediatamente al collegamento selezionato.

* `this`: Attendi fino a 500 ms per concedere ad AppMeasurement il tempo necessario per inviare una richiesta di immagine. Valore predefinito.
* `true`: Non aspetti. Se il collegamento si allontana dalla pagina, è possibile che non venga inviata alcuna richiesta di immagine.

Il ritardo è necessario solo quando un collegamento esce dalla pagina.

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (obbligatorio)

Il secondo argomento ha tre valori validi a seconda del tipo di collegamento che si desidera acquisire. Determina quale dimensione in Adobe Analytics viene compilata dalla richiesta di immagini.

* `d`: Download dei file
* `e`: Esci dai collegamenti
* `o`: Collegamenti personalizzati

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName (obbligatorio)

Questo argomento può essere qualsiasi valore personalizzato fino a 100 byte. Determina il valore della dimensione nel reporting.

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides (facoltativo)

Consente di modificare i valori variabili per una singola chiamata. Se si utilizza l'argomento doneAction e non sono presenti sostituzioni di variabili, utilizzare `null`.

### doneAction (facoltativo)

Specifica un'azione di navigazione da eseguire al termine della chiamata di tracciamento dei collegamenti. Richiede l'utilizzo di `s.useForcedLinkTracking` e `s.forcedLinkTrackingTimeout`. La variabile doneAction può essere la stringa `navigate`, che determina l'impostazione del metodo `document.location` sull'attributo href di `linkObject`. La variabile doneAction può anche essere una funzione che consente una personalizzazione avanzata.

Se si fornisce un valore per doneAction in un `onClick` evento di ancoraggio, è necessario tornare `false` dopo la `s.tl` chiamata per impedire la navigazione predefinita del browser.
Per eseguire il mirroring del comportamento predefinito e seguire l'URL specificato dall'attributo href, fornire una stringa di `navigate` come doneAction. Facoltativamente, è possibile fornire la propria funzione per gestire l'evento di navigazione passando questa funzione come doneAction.

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## Utilizzo delle funzioni JavaScript con il tracciamento dei collegamenti

È possibile consolidare il codice di tracciamento dei collegamenti in una funzione JavaScript indipendente definita sulla pagina o in un file JavaScript collegato. È quindi possibile effettuare chiamate nella funzione onClick di ogni collegamento.

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## Evitare il conteggio dei collegamenti duplicati {#section_9C3F73DE758F4727943439DED110543C}

È possibile che i collegamenti contino due volte in situazioni in cui il collegamento viene normalmente catturato dal download automatico dei file o dal tracciamento dei collegamenti in uscita. Ad esempio, se esegui il tracciamento automatico dei download PDF, una `s.tl` chiamata genera un numero di download duplicato:

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

Per evitare il doppio conteggio dei collegamenti, utilizzate la seguente funzione JavaScript modificata:

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
