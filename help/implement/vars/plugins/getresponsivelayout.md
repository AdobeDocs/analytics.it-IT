---
title: getResponsiveLayout
description: Determinare il layout di un sito Web visualizzato.
feature: Appmeasurement Implementation
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 8%

---

# Plug-in Adobe: getResponsiveLayout

{{plug-in}}

Il plug-in `getResponsiveLayout` consente di tenere traccia della versione del sito Web reattivo basato sulla progettazione che un visitatore sta attualmente guardando. Adobe consiglia di utilizzare questo plug-in se il sito utilizza la progettazione reattiva e se desideri tenere traccia della versione del sito visualizzata da un visitatore. Questo plug-in non è necessario se il sito non utilizza la progettazione reattiva.

## Installare il plug-in utilizzando l’estensione Web SDK o Web SDK

Questo plug-in non è ancora supportato per l&#39;utilizzo in Web SDK.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Initialize Plug-ins&quot; (Inizializza plug-in) con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Library Loaded (Page Top)
1. Aggiungi un’azione alla regola precedente con la seguente configurazione:
   * Estensione: Common Analytics Plugins
   * Tipo azione: inizializzare getResponsiveLayout
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Configure tracking using custom code], che mostra il pulsante [!UICONTROL Open Editor].
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiare e incollare il codice seguente in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta Adobe a risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `getResponsiveLayout` utilizza i seguenti argomenti:

* **`ppw`** (obbligatorio, numero intero): la larghezza massima di pixel che una finestra del browser può avere prima che la pagina passi da un layout con orientamento verticale a un layout con orientamento orizzontale nel telefono
* **`plw`** (obbligatorio, numero intero): la larghezza massima di pixel che una finestra del browser può avere prima che la pagina passi da un layout orizzontale per telefoni a un layout basato su tablet
* **`tw`** (obbligatorio, numero intero): la larghezza massima di pixel consentita per una finestra del browser prima che la pagina passi da un layout tablet a uno desktop

La chiamata di questa funzione restituisce una stringa contenente due parti delimitate da due punti (`:`). La prima parte della stringa contiene uno dei seguenti valori, a seconda della larghezza del browser e degli argomenti sopra riportati:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (per i siti che non dispongono di layout sia verticale che orizzontale)
* `"tablet layout"`
* `"desktop layout"`

La seconda parte della stringa restituita è costituita dalle dimensioni di larghezza e altezza del browser. Ad esempio: `"desktop layout:1243x700"`.

## Esempi

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## Cronologia versioni

### 1.1 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (2 maggio 2018)

* Versione iniziale.
