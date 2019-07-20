---
title: Integra modulo
seo-title: Integrare modulo per Adobe Analytics
description: Il modulo Integra modulo consente ai partner Adobe di integrare i propri sforzi di raccolta dati con l'organizzazione.
seo-description: Il modulo Integra modulo consente ai partner Adobe di integrare i propri sforzi di raccolta dati con l'organizzazione.
translation-type: tm+mt
source-git-commit: dae73042ace20eded9d0caf690a14203827f903a

---


# Integra modulo

Il modulo Integra modulo consente ai partner Adobe di integrare i propri sforzi di raccolta dati con l'organizzazione. Questa integrazione fornisce l'opportunità di una connessione dati bidirezionale. In genere, l'utilizzo del modulo Integra è guidato da un partner Adobe.

> [!NOTE] La richiesta di dati partner nella tua implementazione può aumentare i ritardi tra il carico della pagina e i dati inviati ai server di raccolta dati Adobe. Se un visitatore carica una nuova pagina prima dell'invio dei dati, tale pagina non viene registrata.

## Flusso di lavoro Integra modulo

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. L'oggetto JSON viene restituito.
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. Viene inviata una richiesta di immagine ai server di raccolta dati Adobe.

## Integrare l'implementazione del modulo

Un'organizzazione che utilizza un partner Adobe può utilizzare questi passaggi per iniziare a utilizzare il modulo Integra modulo.

### Ottenere il codice di integrazione del modulo

Per ottenere il codice del modulo è necessario che un utente sia dotato dell'accesso al prodotto o che appartenga a un profilo di prodotto con accesso a Code Manager. Il metodo per ottenere il codice del modulo è lo stesso per tutti i metodi di implementazione, incluso Adobe Experience Platform Launch.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Fai clic sull'icona 9 quadrati in alto a destra, quindi fai clic sul logo di Analytics colorato.
1. In the top navigation, click [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. Scarica la libreria javascript appmeasurement più recente.
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### Inserire il modulo Integra nella propria implementazione

L'implementazione del modulo Integra sul sito richiede l'accesso ad Adobe Experience Platform Launch. Se utilizzi un'implementazione javascript legacy, è necessario accedere al codice sorgente del sito Web dell'organizzazione.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Fate clic sulla proprietà Lancio che intendete modificare.
3. Fate clic sulla scheda Estensioni, quindi su Configura in Adobe Analytics.
4. Aprite il pannellò Configure Tracker using custom codè(Configura il tracciatore utilizzando il codice personalizzato), quindi fate clic su '&lt;/&gt; Open Editor '.
5. Incollate il codice di integrazione del modulo nella finestra modale del codice. Fate clic su Salva una volta completata.

## Integrare i metodi del modulo

Una volta implementato il modulo Integrazione, utilizzate questi metodi per configurarli in modo da inviare e ricevere dati dal partner Adobe desiderato.

### add

The `add` method instantiates a partner object, which serves as an intermediate store of variable data when sharing data between partner systems and your implementation. Questo metodo è richiesto per tutte le integrazioni. Un oggetto partner separato deve essere utilizzato per ogni partner univoco se più partner vengono utilizzati con un'unica implementazione.

```JavaScript
s.Integrate.add("<partner_name>");
```

In genere, la tua organizzazione collabora con un partner Adobe per determinare il valore del nome partner.

### beacon

The `beacon` method creates an image request and points it to the specified URL. Queste richieste di immagini sono diverse dalle richieste standard di immagini. Il metodo beacon invia in genere dati al partner Adobe invece dei server di raccolta dati Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

In genere, la tua organizzazione collabora con il partner Adobe per determinare il valore del nome partner. Le stringhe di query incluse nell'URL sono facoltative e dipendenti dal partner. Il modulo Integra automaticamente una stringa query contenente un numero casuale per impedire la memorizzazione nella cache del browser.

### delay

Adobe sta collaborando internamente con i team per documentare questo metodo.

### get

The `get` method lets a client import partner variables and store them in the partner object. Una volta che i dati si trovano nell'oggetto partner, possono essere assegnati alle variabili Analytics e inviati in una richiesta di immagine. Questo metodo chiama un URL, che punta a un oggetto JSON contenente dati desiderati.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nome partner:** In genere, la tua organizzazione collabora con il partner Adobe per determinare il valore del nome partner.
* **URL all'oggetto JSON:** L'URL a un oggetto JSON che contiene le variabili del partner da includere in una richiesta di immagine.
* **Parametri stringa query:** Informazioni sull'account partner che identificano la tua organizzazione nel sistema del partner. Il partner Adobe usa queste informazioni per identificare il set di dati.

Il modulo Integra aggiunge automaticamente ulteriori stringhe di query all'URL. Una stringa di query var specifica il nome dell'oggetto JSON che il modulo attende dal partner. Viene inoltre aggiunto un numero casuale per impedire la memorizzazione nella cache del browser.

### ready

Adobe sta collaborando internamente con i team per documentare questo metodo.

### Usevars

The `useVars` method lets the client share variable values with an Adobe partner.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

In genere, la tua organizzazione collabora con un partner Adobe per determinare i valori del nome partner e delle variabili utilizzate dal partner.

### Setvars

The `setVars` method lets the client populate Analytics variables using partner data retrieved. Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

In genere, la tua organizzazione collabora con un partner Adobe per determinare i valori del nome partner e delle variabili utilizzate dal partner.

### script

The `script` method lets an Adobe partner to call additional JavaScript from the partner site if certain conditions are met (for example, if the campaign variable is set).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

In genere, la tua organizzazione collabora con il partner Adobe per determinare il valore del nome partner. Le stringhe di query incluse nell'URL sono facoltative e dipendenti dal partner. Il modulo Integra automaticamente una stringa query contenente un numero casuale per impedire la memorizzazione nella cache del browser.
