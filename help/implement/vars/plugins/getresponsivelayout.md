---
title: getResponsiveLayout
description: Determinare il layout di un sito Web attualmente in fase di visualizzazione.
translation-type: tm+mt
source-git-commit: 16d2bc13a71dfe0b9106dea03da5eaa9da4d704c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 1%

---


# Plug-in di Adobe: getResponsiveLayout

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getResponsiveLayout` consente di monitorare quale versione del sito web dinamico basato sulla progettazione sta attualmente esaminando un visitatore. Adobe consiglia di utilizzare questo plug-in se il sito utilizza una progettazione reattiva e desideri tenere traccia della versione del sito visualizzata da un visitatore. Questo plug-in non è necessario se il sito non utilizza design reattivo.

## Installare il plug-in utilizzando l’estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getResponsiveLayout
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato di Launch

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi il [!UICONTROL Configure tracking using custom code] pannello a soffietto, che mostra il pulsante [!UICONTROL Open Editor] .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getResponsiveLayout` utilizza i seguenti argomenti:

* **`ppw`** (obbligatorio, numero intero): Larghezza massima dei pixel che una finestra del browser può avere prima che la pagina passi da un layout di ritratto del telefono a un layout basato su orizzontale del telefono
* **`plw`** (obbligatorio, numero intero): Larghezza massima dei pixel che una finestra del browser può avere prima che la pagina passi dal layout orizzontale del telefono a quello basato su tablet
* **`tw`** (obbligatorio, booleano): Larghezza massima dei pixel che una finestra del browser può avere prima che la pagina passi da un layout tablet a un layout basato su desktop

Se si richiama questo metodo, viene restituita una stringa contenente due parti. La prima parte utilizza uno dei seguenti valori, a seconda della larghezza del browser e degli argomenti di cui sopra:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (per i siti che non dispongono sia di layout verticale che orizzontale)
* `"tablet layout"`
* `"desktop layout"`

La seconda parte della stringa restituita sono le dimensioni di larghezza e altezza del browser. Ad esempio, `"desktop layout:1243x700"`.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

* Il sito passa dalla modalità verticale del telefono alla modalità orizzontale del telefono quando la larghezza del browser è maggiore di 500 pixel
* Il sito passa dalla modalità orizzontale del telefono alla modalità tablet quando la larghezza del browser è maggiore di 700 pixel
* Il sito passa dalla modalità tablet alla modalità desktop quando la larghezza del browser è superiore a 1000 pixel

...il codice seguente imposta eVar10 come layout di progettazione reattiva corrente e come esperienza del visitatore, nonché la larghezza e le dimensioni del browser.

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Esempio n. 3

Se viene mostrato...

* Il sito dispone solo di una modalità telefono, tablet e desktop
* Il sito passa dalla modalità telefono alla modalità tablet quando la larghezza del browser è superiore a 500 pixel
* Il sito passa dalla modalità tablet alla modalità desktop quando la larghezza del browser è superiore a 1.100 pixel

...il codice seguente imposta eVar10 come layout di progettazione reattiva corrente e come esperienza del visitatore, nonché la larghezza e le dimensioni del browser.

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Cronologia versioni

### 1.1 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (2 maggio 2018)

* Versione iniziale.
