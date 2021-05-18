---
title: Integrate Module
description: Il modulo Integrate Module consente ai partner di Adobe di integrare le attività di raccolta dei dati con la tua organizzazione.
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 4%

---

# Integrate Module

Il modulo Integrate Module consente ai partner di Adobe di integrare le attività di raccolta dei dati con la tua organizzazione. Questa integrazione offre l’opportunità di effettuare una connessione dati bidirezionale. In genere, l’utilizzo del modulo Integrate è guidato da un partner di Adobe.

>[!NOTE]
>
>La richiesta di dati partner nell’implementazione può aumentare i ritardi tra il caricamento della pagina e i dati inviati ai server di raccolta dati di Adobe. Se un visitatore carica una nuova pagina prima dell’invio dei dati, questa non viene registrata.

## Flusso di lavoro del modulo Integrate

1. Un visitatore del sito carica una pagina che avvia una richiesta `get` per i dati del partner.
2. Il partner di Adobe riceve la richiesta `get` e crea il pacchetto delle variabili appropriate in un oggetto JSON. Viene restituito l’oggetto JSON.
3. Il sito riceve l’oggetto JSON e chiama `setVars` per assegnare le informazioni contenute nell’oggetto JSON alle variabili Adobe Analytics
4. Viene inviata una richiesta di immagine ai server di raccolta dati di Adobe.

## Implementazione del modulo Integrate

Un&#39;organizzazione che lavora con un partner di Adobe può utilizzare questi passaggi per iniziare a utilizzare correttamente il modulo Integrate.

### Ottieni codice modulo integrato

Per ottenere il codice del modulo è necessario un utente con accesso Amministratore prodotto o appartenente a un profilo di prodotto con accesso a Code Manager. Il metodo per ottenere il codice del modulo è lo stesso per tutti i metodi di implementazione, incluso Adobe Experience Platform Launch.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
1. Nella navigazione in alto, fai clic su **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]**.
1. Scarica la libreria AppMeasurement JavaScript più recente.
1. Una volta scaricato, decomprimi il file e individua `AppMeasurement_Module_Integrate.js`.

### Inserire il modulo Integrate nell’implementazione

L’implementazione del modulo Integrate sul sito richiede l’accesso ad Adobe Experience Platform Launch. Se utilizzi un’implementazione JavaScript legacy, è necessario accedere al codice sorgente del sito web dell’organizzazione.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali Adobe ID.
2. Fai clic sulla proprietà Launch che desideri modificare.
3. Fai clic sulla scheda Estensioni , quindi fai clic su Configura sotto Adobe Analytics.
4. Apri il pannello a soffietto &quot;Configura il tracker utilizzando codice personalizzato&quot;, quindi fai clic su &quot;&lt;/> Apri editor&quot;.
5. Incolla il codice del modulo Integrate nella finestra modale del codice. Fai clic su Salva una volta completato.

## Metodi di integrazione del modulo

Una volta implementato il modulo Integrate, utilizza questi metodi per configurarlo per inviare e ricevere dati dal partner di Adobe desiderato.

### add

Il metodo `add` crea un&#39;istanza di un oggetto partner, che funge da archivio intermedio di dati variabili durante la condivisione di dati tra i sistemi partner e l&#39;implementazione. Questo metodo è necessario per tutte le integrazioni. Se più partner vengono utilizzati in un’unica implementazione, è necessario utilizzare un oggetto partner separato per ciascun partner univoco.

```JavaScript
s.Integrate.add("<partner_name>");
```

In genere, l’organizzazione collabora con un partner di Adobe per determinare il valore del nome del partner.

### beacon

Il metodo `beacon` crea una richiesta di immagine e la indirizza all’URL specificato. Queste richieste di immagini sono diverse dalle richieste di immagini standard. Il metodo beacon invia in genere i dati al partner Adobe anziché ai server di raccolta dati Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

In genere, l’organizzazione collabora con il partner di Adobe per determinare il valore del nome del partner. Le stringhe di query incluse nell’URL sono facoltative e dipendono dal partner. Il modulo Integrate include automaticamente una stringa di query contenente un numero casuale per impedire il caching del browser.

### ritardare

Adobe sta lavorando internamente con i team per ottenere la documentazione di questo metodo.

### get

Il metodo `get` consente a un client di importare le variabili del partner e archiviarle nell&#39;oggetto partner. Una volta che i dati si trovano nell’oggetto partner, possono essere assegnati alle variabili di Analytics e inviati in una richiesta di immagine. Questo metodo chiama un URL, che punta a un oggetto JSON contenente i dati desiderati.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nome partner:** la tua organizzazione in genere collabora con il partner di Adobe per determinare il valore del nome del partner.
* **URL dell’oggetto JSON:** l’URL di un oggetto JSON che contiene le variabili partner da incorporare in una richiesta di immagine.
* **Parametri della stringa di query:** informazioni sull’account partner che identificano la tua organizzazione nel sistema del partner. Il partner di Adobe utilizza queste informazioni per identificare il set di dati.

Il modulo Integrate aggiunge automaticamente ulteriori stringhe di query all’URL. Una stringa di query var specifica il nome dell&#39;oggetto JSON che il modulo si aspetta di nuovo dal partner. Viene inoltre aggiunto un numero casuale per impedire la memorizzazione in cache del browser.

### ready

Adobe sta lavorando internamente con i team per ottenere la documentazione di questo metodo.

### useVars

Il metodo `useVars` consente al client di condividere i valori delle variabili con un partner di Adobe.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

In genere, la tua organizzazione collabora con un partner di Adobe per determinare i valori per il nome del partner e le variabili utilizzate dal partner.

### setVars

Il metodo `setVars` consente al client di popolare le variabili di Analytics utilizzando i dati del partner recuperati. I dati dei partner possono essere il risultato di un metodo `get`, di un&#39;assegnazione statica o di qualsiasi altro meccanismo che popola l&#39;oggetto partner con i dati.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

In genere, la tua organizzazione collabora con un partner di Adobe per determinare i valori per il nome del partner e le variabili utilizzate dal partner.

### script

Il metodo `script` consente a un partner di Adobe di chiamare un codice JavaScript aggiuntivo dal sito partner se vengono soddisfatte determinate condizioni (ad esempio, se la variabile della campagna è impostata).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

In genere, l’organizzazione collabora con il partner di Adobe per determinare il valore del nome del partner. Le stringhe di query incluse nell’URL sono facoltative e dipendono dal partner. Il modulo Integrate include automaticamente una stringa di query contenente un numero casuale per impedire il caching del browser.
