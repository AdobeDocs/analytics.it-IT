---
title: Integrare il modulo
description: Il modulo Integra consente ai partner Adobi di integrare le attività di raccolta dati con l’organizzazione.
feature: Variables
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 4%

---

# Integrare il modulo

Il modulo Integra consente ai partner Adobi di integrare le attività di raccolta dati con l’organizzazione. Questa integrazione offre l’opportunità di una connessione dati bidirezionale. In genere, l’utilizzo del modulo di integrazione è gestito da un partner Adobe.

>[!NOTE]
>
>La richiesta dei dati dei partner nell’implementazione può aumentare i ritardi tra il caricamento delle pagine e l’invio dei dati ai server di raccolta dati di Adobe. Se un visitatore carica una nuova pagina prima dell’invio dei dati, la pagina non viene registrata.

## Integrare il flusso di lavoro del modulo

1. Un visitatore del sito carica una pagina che avvia una richiesta `get` per dati partner.
2. Il partner Adobe riceve la richiesta `get` e crea un pacchetto delle variabili appropriate in un oggetto JSON. Viene restituito l’oggetto JSON.
3. Il sito riceve l&#39;oggetto JSON e chiama `setVars` per assegnare le informazioni contenute nell&#39;oggetto JSON alle variabili di Adobe Analytics
4. Viene inviata una richiesta di immagine ai server di raccolta dati Adobe.

## Implementazione del modulo di integrazione

Un’organizzazione che lavora con un partner Adobe può utilizzare questi passaggi per iniziare a utilizzare correttamente il modulo di integrazione.

### Ottieni il codice del modulo integrato

Per ottenere il codice del modulo è necessario avere accesso come amministratore di prodotto oppure appartenere a un profilo di prodotto con accesso al Code Manager. Il metodo per ottenere il codice del modulo è lo stesso per tutti i metodi di implementazione, inclusi i tag in Adobe Experience Platform.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
1. Nella navigazione in alto, fai clic su **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]**.
1. Scarica la libreria di AppMeasurement più recente di JavaScript.
1. Una volta scaricato, decomprimere il file e individuare `AppMeasurement_Module_Integrate.js`.

### Posizionare il modulo Integrate nell’implementazione

L’implementazione del modulo di integrazione sul sito richiede l’accesso a Raccolta dati di Adobe Experience Platform. Se utilizzi un’implementazione legacy di JavaScript, è necessario accedere al codice sorgente del sito web della tua organizzazione.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà tag che desideri modificare.
1. Fai clic sulla scheda Estensioni, quindi fai clic su Configura in Adobe Analytics.
1. Apri il pannello a soffietto &quot;Configura il tracciatore con codice personalizzato&quot;, quindi fai clic su &quot;&lt;/> Apri editor&quot;.
1. Incolla il codice del modulo di integrazione nella finestra modale del codice. Una volta completato, fai clic su Salva.

## Integrare i metodi del modulo

Una volta implementato il modulo Integrate, puoi configurarlo per inviare e ricevere dati dal partner Adobe desiderato.

### aggiungi

Il metodo `add` crea un&#39;istanza di un oggetto partner, che funge da archivio intermedio di dati variabili durante la condivisione di dati tra sistemi partner e l&#39;implementazione. Questo metodo è necessario per tutte le integrazioni. Se in una singola implementazione vengono utilizzati più partner, è necessario utilizzare un oggetto partner separato per ogni partner univoco.

```JavaScript
s.Integrate.add("<partner_name>");
```

In genere, l’organizzazione collabora con un partner Adobe per determinare il valore del nome del partner.

### beacon

Il metodo `beacon` crea una richiesta di immagine e la punta all&#39;URL specificato. Queste richieste di immagini sono diverse dalle richieste di immagini standard. In genere, il metodo beacon invia i dati al partner Adobe anziché ai server di raccolta dati Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

In genere, l’organizzazione collabora con il partner Adobe per determinare il valore del nome del partner. Le stringhe di query incluse nell’URL sono facoltative e dipendenti dal partner. Il modulo di integrazione include automaticamente una stringa di query contenente un numero casuale per impedire la memorizzazione nella cache del browser.

### ritardo

Adobe sta lavorando con i team internamente per documentare questo metodo.

### get

Il metodo `get` consente a un client di importare variabili partner e di memorizzarle nell&#39;oggetto partner. Una volta che i dati sono nell’oggetto partner, possono essere assegnati alle variabili Analytics e inviati in una richiesta di immagine. Questo metodo chiama un URL che punta a un oggetto JSON contenente i dati desiderati.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nome partner:** In genere l&#39;organizzazione collabora con il partner Adobe per determinare il valore per il nome del partner.
* **URL dell&#39;oggetto JSON:** URL di un oggetto JSON contenente le variabili partner da incorporare in una richiesta di immagine.
* **Parametri stringa di query:** Informazioni sull&#39;account partner che identificano l&#39;organizzazione nel sistema del partner. Il partner Adobe utilizza queste informazioni per identificare il set di dati.

Il modulo Integra aggiunge automaticamente più stringhe di query all’URL. Una stringa di query var specifica il nome dell’oggetto JSON che il modulo si aspetta dal partner. Viene aggiunto anche un numero casuale per impedire il caching del browser.

### pronto

Adobe sta lavorando con i team internamente per documentare questo metodo.

### useVars

Il metodo `useVars` consente al client di condividere i valori delle variabili con un partner Adobe.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

In genere, l’organizzazione collabora con un partner Adobe per determinare i valori per il nome del partner e le variabili utilizzate dal partner.

### setVars

Il metodo `setVars` consente al client di popolare le variabili di Analytics utilizzando i dati partner recuperati. I dati partner possono essere il risultato di un metodo `get`, di un&#39;assegnazione statica o di qualsiasi altro meccanismo che popola l&#39;oggetto partner con i dati.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

In genere, l’organizzazione collabora con un partner Adobe per determinare i valori per il nome del partner e le variabili utilizzate dal partner.

### script

Il metodo `script` consente a un partner Adobe di chiamare JavaScript aggiuntivo dal sito partner se vengono soddisfatte determinate condizioni (ad esempio, se è impostata la variabile della campagna).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

In genere, l’organizzazione collabora con il partner Adobe per determinare il valore del nome del partner. Le stringhe di query incluse nell’URL sono facoltative e dipendenti dal partner. Il modulo di integrazione include automaticamente una stringa di query contenente un numero casuale per impedire la memorizzazione nella cache del browser.
