---
title: Integrate Module
description: Il modulo Integrate consente ai partner Adobe di integrare le attività di raccolta dei dati con la propria organizzazione.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Integrate Module

Il modulo Integrate consente ai partner Adobe di integrare le attività di raccolta dei dati con la propria organizzazione. Questa integrazione offre l'opportunità di una connessione dati bidirezionale. In genere, l'utilizzo del modulo Integrate è gestito da un partner Adobe.

> [!NOTE] La richiesta di dati del partner nell'implementazione può aumentare i ritardi tra il caricamento delle pagine e i dati inviati ai server di raccolta dati Adobe. Se un visitatore carica una nuova pagina prima dell’invio dei dati, la pagina non viene registrata.

## Flusso di lavoro Integrate Module

1. Un visitatore del sito carica una pagina che avvia una `get` richiesta di dati del partner.
2. Il partner Adobe riceve la `get` richiesta e crea il pacchetto delle variabili appropriate in un oggetto JSON. L'oggetto JSON viene restituito.
3. Il sito riceve l'oggetto JSON e richiama `setVars` l'assegnazione delle informazioni contenute nell'oggetto JSON alle variabili di Adobe Analytics
4. Una richiesta di immagine viene inviata ai server di raccolta dati Adobe.

## Implementazione del modulo integrato

Un'organizzazione che collabora con un partner Adobe può utilizzare questi passaggi per iniziare a utilizzare con successo il modulo Integrate.

### Ottieni codice modulo integrato

Per ottenere il codice del modulo è necessario un utente con accesso Amministratore prodotto o che appartenga a un profilo di prodotto con accesso a Gestione codici. Il metodo per ottenere il codice del modulo è lo stesso per tutti i metodi di implementazione, incluso Adobe Experience Platform Launch.

1. Accedete a [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali ID Adobe.
1. Fate clic sull'icona di 9 quadrati in alto a destra, quindi fate clic sul logo Analytics colorato.
1. Nella navigazione in alto, fai clic su [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. Scarica la libreria AppMeasurement JavaScript più recente.
1. Una volta scaricato, decomprimete il file e individuate `AppMeasurement_Module_Integrate.js`.

### Inserire il modulo Integrate nella propria implementazione

L'implementazione del modulo Integrate sul sito richiede l'accesso ad Adobe Experience Platform Launch. Se utilizzate un'implementazione JavaScript precedente, è necessario accedere al codice sorgente del sito Web dell'organizzazione.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali ID Adobe.
2. Fare clic sulla proprietà Launch che si desidera modificare.
3. Fai clic sulla scheda Estensioni, quindi su Configura in Adobe Analytics.
4. Aprite la struttura di navigazione 'Configura tracciamento tramite codice personalizzato', quindi fate clic su '&lt;/&gt; Apri editor'.
5. Incollate il codice Modulo integrato nella finestra modale del codice. Al termine, fate clic su Salva.

## Metodi di integrazione del modulo

Una volta implementato il modulo Integrate, utilizzate questi metodi per configurarlo in modo da inviare e ricevere dati dal partner Adobe desiderato.

### add

Il `add` metodo crea un'istanza di un oggetto partner, che funge da archivio intermedio di dati variabili durante la condivisione di dati tra i sistemi partner e l'implementazione. Questo metodo è richiesto per tutte le integrazioni. Se più partner vengono utilizzati in un'unica implementazione, è necessario utilizzare un oggetto partner separato per ciascun partner univoco.

```JavaScript
s.Integrate.add("<partner_name>");
```

La vostra organizzazione in genere lavora con un partner Adobe per determinare il valore del nome del partner.

### beacon

Il `beacon` metodo crea una richiesta di immagine e la indirizza all’URL specificato. Queste richieste di immagini sono diverse dalle richieste di immagini standard. In genere, il metodo beacon invia i dati al partner Adobe anziché ai server di raccolta dei dati Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

 La vostra organizzazione collabora solitamente con il partner Adobe per determinare il valore del nome del partner. Le stringhe di query incluse nell'URL sono facoltative e dipendono dal partner. Il modulo Integrate include automaticamente una stringa di query contenente un numero casuale per impedire il caching del browser.

### delay

Adobe sta collaborando con i team interni per documentare questo metodo.

### get

Il `get` metodo consente a un client di importare le variabili del partner e di memorizzarle nell'oggetto partner. Una volta che i dati sono nell’oggetto partner, possono essere assegnati alle variabili Analytics e inviati in una richiesta di immagine. Questo metodo chiama un URL, che punta a un oggetto JSON contenente i dati desiderati.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **** Nome partner: La vostra organizzazione collabora solitamente con il partner Adobe per determinare il valore del nome del partner.
* **** URL dell'oggetto JSON: L'URL di un oggetto JSON che contiene le variabili partner da incorporare in una richiesta di immagine.
* **** Parametri stringa query: Informazioni sull'account del partner che identificano l'organizzazione nel sistema del partner. Il partner Adobe utilizza queste informazioni per identificare il set di dati.

Il modulo Integrate aggiunge automaticamente ulteriori stringhe di query all’URL. Una stringa di query var specifica il nome dell'oggetto JSON che il modulo si aspetta di nuovo dal partner. È stato aggiunto anche un numero casuale per impedire il caching dei browser.

### ready

Adobe sta collaborando con i team interni per documentare questo metodo.

### useVars

Questo `useVars` metodo consente al client di condividere i valori delle variabili con un partner Adobe.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

In genere l’organizzazione lavora con un partner Adobe per determinare i valori per il nome del partner e le variabili utilizzate dal partner.

### setVars

Questo `setVars` metodo consente al client di compilare le variabili Analytics utilizzando i dati del partner recuperati. I dati dei partner possono essere il risultato di un `get` metodo, un'assegnazione statica o qualsiasi altro meccanismo che compili l'oggetto partner con i dati.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

In genere l’organizzazione lavora con un partner Adobe per determinare i valori per il nome del partner e le variabili utilizzate dal partner.

### script

Questo `script` metodo consente a un partner Adobe di chiamare JavaScript aggiuntivo dal sito partner se determinate condizioni sono soddisfatte (ad esempio, se la variabile della campagna è impostata).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

 La vostra organizzazione collabora solitamente con il partner Adobe per determinare il valore del nome del partner. Le stringhe di query incluse nell'URL sono facoltative e dipendono dal partner. Il modulo Integrate include automaticamente una stringa di query contenente un numero casuale per impedire il caching del browser.
